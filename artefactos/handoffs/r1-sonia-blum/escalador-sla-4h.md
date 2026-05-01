# ⏱ Escalador SLA 4h — R1 caliente

> El blueprint Make (`escenario-r1-sonia-blum.json`) ya tiene los módulos de escalado integrados. Esta nota documenta cómo funciona y cómo testearlos por separado.

## Lógica del escalador (ya en el blueprint)

```
Lead entra
   │
   ├─► Notifica owner N1 (módulo 8)
   │
   ▼
Sleep SLA horas (módulo 9)  ──── 4h si caliente, 24h si tibio
   │
   ▼
Check estado en Notion (módulo 10)
   │
   ▼
Router (módulo 11)
   │
   ├─► Estado = "En curso" o "Cerrado" → OK, fin
   │
   └─► Estado = "Pendiente" → SLA VENCIDO
            │
            ├─► Email alerta a CEO (módulo 12)
            └─► Update Notion estado = "Vencido N1 - escalado N2" (módulo 13)
```

## Niveles de escalado

| Nivel | Cuando se dispara | Destinatario | Acción |
|---|---|---|---|
| **N1 (Owner)** | T+0 al recibir lead | Owner Blum + CC CEO | Notificación inicial |
| **N2 (Pdte. Blum)** | T+SLA si N1 no actúa | Pdte. Blum + CC CEO | Email de alerta · estado Notion → "Vencido N1" |
| **N3 (CEO)** | T+(SLA + 24h) si N2 tampoco | CEO directo | Brief ejecutivo · estado → "Vencido N2 - escalado CEO" |

> Para implementar N3 completo, duplicar los módulos 9-13 con un segundo `Sleep` de 24h y un segundo router. Lo dejo como Sprint 1.5 — la versión actual cubre N1→N2 que es lo crítico.

## Excepciones del escalador

1. **Bloque intocable** martes 16:00–19:00 Austria: el sleep se extiende automáticamente hasta miércoles 09:00.
   - Implementación: módulo `util:DateAdd` antes del Sleep que detecta si el deadline cae en bloque intocable y lo posterga.
2. **Crisis cliente**: si el lead viene marcado con `urgencia=crisis`, salta directo a CEO sin esperar SLA.
3. **Día bajo CEO**: si la CEO marca el día como "bajo" en una variable de Make (manual toggle), las alertas se acumulan y se entregan al día siguiente en el primer pico de energía.

## Test del escalador

### Test 1 — flujo OK
1. Mandar lead de prueba con `urgencia=caliente`.
2. **Antes de las 4h**, marcar estado en Notion = `En curso`.
3. ✅ El escalador no debe disparar alerta.

### Test 2 — flujo vencido
1. Mandar lead de prueba con `urgencia=caliente`.
2. **NO tocar Notion**. Esperar 4h.
3. ✅ Debe llegar email de alerta a CEO.
4. ✅ Estado en Notion debe cambiar a `Vencido N1 - escalado N2`.

### Test 3 — bloque intocable
1. Mandar lead de prueba un martes a las 13:00 Austria con SLA 4h (vencería 17:00, dentro del bloque intocable 16-19h).
2. ✅ El escalador debe disparar el miércoles a las 09:00 Austria, no el martes a las 17:00.

## Variables de configuración (Make)

```
SLA_HORAS_CALIENTE = 4
SLA_HORAS_TIBIO = 24
SLA_HORAS_N2 = 24                 (extra después de N1)
TIMEZONE_CEO = Europe/Vienna
BLOQUE_INTOCABLE_DIA = TUESDAY
BLOQUE_INTOCABLE_INICIO = 16:00
BLOQUE_INTOCABLE_FIN = 19:00
```

Estas variables se setean en el módulo 2 (`util:SetVariables`) para no hardcodearlas.

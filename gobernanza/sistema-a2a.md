# 🔗 Sistema A2A — Arquitectura de handoffs entre marcas

> Versión 1.0 · Modelo A (Holding Centralizado) · 1-may-2026.
> 4 marcas · 6 rutas A2A · 3 niveles de SLA · 0 canibalización.

## Estructura del holding

```
                 CEO (Sonia Yánez Blum)
                          │
   ┌──────────────────────┼──────────────────────┐
   ▼                      ▼                      ▼
SONIA YÁNEZ          BLUM DIGITAL PR        ACADEMIA ARP
(personal)           (consultoría B2B2C)    (educativa B2C)
   │                      │                      │
   └──── 6 rutas A2A activas ──── conectadas ────┘

                              │
                       SONJA KALOS
                       (silo · 0 rutas)
                       — separación estricta por diseño —
```

## Las 6 rutas A2A activas

| Ruta | Origen → Destino | Tipo | SLA máximo (Owner N1) | Volumen esperado / mes | Valor estratégico |
|---|---|---|---|---|---|
| **R1** | Sonia → Blum | Comercial — lead consultoría | 4h hábiles caliente / 24h tibio | 3-8 leads | 🟢 ALTO — convierte audiencia en ingresos |
| **R2** | Sonia → ARP | Comercial — lead formación | 24h hábiles | 5-15 leads | 🟡 MEDIO — escala con poco margen unitario |
| **R3** | Blum → Sonia | Contenido — caso de éxito anonimizado | 5 días hábiles | 1-3 casos | 🟢 ALTO — alimenta papers, podcast, columna |
| **R4** | Blum → ARP | Comercial — capacitar equipo del cliente | 48h hábiles | 1-2 oportunidades | 🟡 MEDIO — incrementa ticket por cliente |
| **R5** | ARP → Sonia | Contenido — insight pedagógico | 7 días hábiles | 1-2 insights | 🟡 MEDIO — alimenta investigación doctoral |
| **R6** | ARP → Blum | Comercial — alumno → consultoría premium | 24h hábiles | 1-3 leads | 🟢 ALTO — convierte alumno en cliente premium |

> **Sonja Kalos**: 0 handoffs — separación estricta por diseño (firewall absoluto).

## Lógica de retroalimentación

> La **marca personal** (Sonia) trae leads a las marcas operativas (R1, R2). Las marcas operativas devuelven a la marca personal contenido académicamente útil (R3, R5). Entre las marcas operativas se referencian alumnos premium y formación corporativa (R4, R6). Sonja Kalos vive aparte.

## Implementación en 3 sprints

| Sprint | Foco | Rutas | Skills nuevos |
|---|---|---|---|
| **Sprint 1** | Rutas comerciales — palanca ingresos directa | R1, R2, R6 | `enrutador-handoff-a2a` |
| **Sprint 2** | Ruta cross + monitoreo | R4 | `monitor-sla-a2a` · `escalador-ceo-a2a` · `detector-canibalizacion` |
| **Sprint 3** | Rutas de contenido + métricas mensuales | R3, R5 | dashboard A2A mensual |

Detalle del estado por sprint en `PENDIENTES.md`.

## Datos de cada handoff (formato estándar)

Toda ruta A2A registra:

- **ID** del handoff (UUID).
- **Origen** y **destino** (marca + presidente dueño).
- **Tipo** (comercial caliente / comercial tibio / contenido / cross).
- **Fecha y hora** de creación.
- **SLA máximo** según matriz (`sla-handoff.md`).
- **Owner N1** (subagente o presidente que recibe).
- **Estado** (pendiente / en curso / cerrado / escalado / vencido).
- **Resultado** (convertido / archivado / rechazado).
- **Notas** (contexto, links, capturas).

Implementación CRM: campos en Notion (esquema pendiente).

## Reglas del sistema

1. Todo handoff lleva owner N1 al crearse.
2. Si vence N1 → escala automáticamente al Presidente correspondiente (N2).
3. Si vence N2 → escala automáticamente a la CEO (N3).
4. Crisis cliente → SLA inmediato, salta a N3 sin esperar.
5. **Bloque intocable**: martes 16:00–19:00 Austria. Ningún SLA exige acción en ese bloque. Si vence dentro, espera al miércoles 09:00 Austria.
6. Toda violación de las **3 reglas anti-canibalización** → bloqueo automático del handoff + alerta crítica a la CEO.

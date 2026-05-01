# 🚨 Respuesta a incidentes — runbook 4 horas

> Si algo se compromete (cuenta, dato filtrado, chat IA secuestrado, firewall roto), los primeros 60 minutos cuentan. Este runbook es para no pensar bajo presión.

## Severidad

| Nivel | Ejemplo | SLA |
|---|---|---|
| **S1 — Crítico** | ATO Gmail Sonia · firewall Sonja Kalos roto · filtración masiva de datos cliente · ransomware · DOI no autorizado citado en prensa | Notificar CEO < 30 min · plan inicial < 2 h · resolución < 24 h |
| **S2 — Alto** | Acceso indebido detectado en Notion · phishing dirigido recibido · scraping masivo · 1 prompt-injection exitoso | Notificar CEO < 2 h · plan inicial < 4 h · resolución < 72 h |
| **S3 — Medio** | Intento de jailbreak fallido logged · credencial caducada · permiso de Drive abierto por error | Notificar siguiente reporte mensual · resolución < 1 semana |

## Runbook S1 — primeros 60 minutos

### 0–10 min: contención
1. **Identifica** qué activo y qué tipo de compromiso.
2. **Aísla**: cierra sesiones activas en la cuenta · pausa el chat IA afectado · desconecta el escenario Make.
3. **Conserva**: no borres logs aún — los necesitas para forensía.

### 10–30 min: notificación
4. **Avisa a la CEO** por canal seguro (no email comprometido). Texto: severidad + activo + impacto estimado + siguiente paso.
5. **Notifica al Pdte. dueño del activo** para que active sus controles.

### 30–60 min: estabilización
6. **Rota credenciales** del activo afectado y de los conectados.
7. **Revoca tokens** API expuestos.
8. **Verifica integridad** de backups recientes.
9. **Mide impacto**: qué se filtró, a quién, durante cuánto.

## Runbook 1–4 horas

### Comunicación
- **Si afectó a clientes/alumnos/panelistas**: borrador de comunicación para que la CEO firme. Plazo legal GDPR breach: 72 h a la autoridad, sin demora a los afectados.
- **Si afectó al firewall Sonja Kalos**: silencio público hasta limpiar la fuga. Solicitar removal a Google/buscadores de cualquier captura/cache.
- **Si fue ATO**: avisar a contactos cercanos para que ignoren mensajes salientes recientes.

### Forensía mínima
- Logs del activo en las 72 h previas.
- Última fecha de acceso legítimo conocido.
- Direcciones IP no reconocidas.
- Cambios recientes en permisos.
- Dispositivos vinculados a la cuenta.

### Recuperación
- Restaurar desde backup limpio si hubo borrado.
- Re-emitir contraseñas y tokens.
- Re-deploy con secretos rotados.
- Test de funcionamiento.

## Runbook 24–72 horas

### Análisis causa raíz (postmortem)
1. **Qué pasó** — narrativa cronológica.
2. **Por qué pudo pasar** — control que falló o no existía.
3. **Cómo lo detectamos** — y cuánto tardamos.
4. **Cómo lo contuvimos**.
5. **Qué cambiamos** para que no vuelva a pasar.
6. **Qué KPI vamos a vigilar** para detectarlo antes la próxima vez.

Postmortem no es para culpar — es para aprender. Documento queda en `seguridad/incidentes/{YYYY-MM-DD}-{nombre}.md` (carpeta privada del repo, no pública).

### Compliance GDPR
- Si hubo brecha de datos personales:
  - Notificar a la **AEPD austríaca (DSB)** dentro de 72 h.
  - Notificar a los afectados sin demora indebida.
  - Documentar todo en registro de brechas (obligatorio aunque no se notifique externamente).

## Plantilla de notificación a CEO

```
🚨 INCIDENTE [S1/S2/S3]
Activo: [Gmail Sonia / WAHA / Notion / Drive / chat Sofía / firewall Sonja Kalos / otro]
Qué pasó: [1 línea]
Cuándo se detectó: [fecha + hora]
Impacto estimado: [datos / personas / sistemas afectados]
Acción tomada hasta ahora: [1 línea]
Siguiente paso (lo necesito de ti): [decisión binaria si aplica]
```

## Plantilla de comunicación a afectados (GDPR breach)

> Borrador inicial — la CEO siempre revisa y firma antes de enviar.

```
Asunto: Aviso importante sobre la seguridad de tus datos

Hola [Nombre],

Te escribimos para informarte de un incidente que afectó la seguridad de
algunos datos personales que tenemos sobre ti.

Qué pasó:
[Descripción factual sin culpa ni tecnicismos]

Cuándo:
[Fecha del incidente] — detectado el [fecha de detección].

Qué datos pudieron verse afectados:
[Lista específica]

Qué hemos hecho:
[Acciones tomadas]

Qué te recomendamos hacer:
[Acciones para el afectado, si aplica: cambio contraseña, monitoreo, etc.]

Cómo contactarnos:
soniayanezblum@gmail.com

Lamentamos profundamente la situación y estamos comprometidos con
mejorar nuestros controles para que no vuelva a ocurrir.

[Firma CEO]
```

## Test trimestral

Simular un incidente cada trimestre (mesa redonda con la CEO):
- Trimestre 1: ATO de Gmail Sonia.
- Trimestre 2: prompt injection exitoso en chat Sofía.
- Trimestre 3: filtración Sonja Kalos en SEO.
- Trimestre 4: ransomware Drive.

Registrar tiempos de detección, contención, comunicación. Mejorar.

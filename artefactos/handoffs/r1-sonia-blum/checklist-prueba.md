# ✅ Checklist de prueba R1 — paso a paso, sin pensar

> Ejecuta los pasos en orden. Marca cada uno al completarlo. Si uno falla, **párate** ahí y resuélvelo antes de seguir.

---

## Fase 1 — preparativos (15-20 min)

- [ ] **1.** Abre Drive de `soniayanezblum@gmail.com`.
- [ ] **2.** Crea la estructura de carpetas según `infraestructura/drive/estructura-pipeline-handoffs.md` (sección "Cómo crearla").
- [ ] **3.** Sube `artefactos/handoffs/r1-sonia-blum/log-handoff.csv` a `AI-HQ/Pipeline/Handoffs/R1-Sonia-Blum/_plantillas/` y conviértelo a `.xlsx` desde Excel/Sheets.
- [ ] **4.** Anota el ID del archivo .xlsx (lo necesitarás más tarde si quieres conectar el log automático).

---

## Fase 2 — Notion CRM (15 min)

- [ ] **5.** Abre Notion y crea una base de datos nueva llamada `Handoffs A2A`.
- [ ] **6.** Crea las propiedades según `artefactos/handoffs/r1-sonia-blum/log-handoff-schema.md` (cada columna del CSV = una propiedad Notion del tipo correspondiente).
- [ ] **7.** Configura una vista filtrada: "Solo R1" (filter: ruta = R1).
- [ ] **8.** Configura otra vista: "SLA en riesgo" (filter: estado = Pendiente AND deadline_n1 < now + 1h).
- [ ] **9.** Anota el `database_id` de Notion (URL → la parte entre / y ?).

---

## Fase 3 — MailerLite (10 min)

- [ ] **10.** Inicia sesión en MailerLite con la cuenta de Blum.
- [ ] **11.** Crea un grupo nuevo: `blum-leads-r1`.
- [ ] **12.** Crea una **automation**: trigger = "Subscriber added to group blum-leads-r1".
- [ ] **13.** Añade el email de acuse al lead. Pega el HTML de `artefactos/handoffs/r1-sonia-blum/email-acuse-lead.md`.
- [ ] **14.** Configura los campos personalizados que necesita: `name`, `company`, `sla_horas`, `handoff_id`.
- [ ] **15.** Activa la automation y manda 1 email de prueba a tu propio email para verificar formato.

---

## Fase 4 — Make (20-30 min)

- [ ] **16.** Inicia sesión en Make.
- [ ] **17.** Scenarios → Create new scenario → "Import blueprint" → sube `infraestructura/make/escenario-r1-sonia-blum.json`.
- [ ] **18.** Cuando Make pida, **autoriza las connections**:
  - Custom Webhook (Make lo crea solo)
  - OpenAI / Anthropic (con tu API key)
  - Google Drive (cuenta `soniayanezblum@gmail.com`)
  - Notion (con tu integration token con acceso a la base `Handoffs A2A`)
  - MailerLite (con tu API key)
  - SMTP / Email (cuenta de envío de notificación interna)
- [ ] **19.** Edita el módulo 1 (Webhook) → copia la URL del hook que Make genera. **Anótala.**
- [ ] **20.** Edita el módulo 2 (SetVariables) → cambia:
  - `owner_n1_email` por el email real del owner Blum N1.
  - `ceo_email` por `soniayanezblum@gmail.com` (verificar).
- [ ] **21.** Edita el módulo 6 (Notion CreatePage) → pega el `database_id` que anotaste en paso 9.
- [ ] **22.** Edita el módulo 7 (MailerLite) → confirma que el grupo es `blum-leads-r1`.
- [ ] **23.** Edita el módulo 8 (Email Send) → pega el HTML/texto de `email-notif-interna.md` en el body.
- [ ] **24.** **Save** el escenario. **NO actives todavía.**

---

## Fase 5 — Test 1: flujo OK (5 min)

- [ ] **25.** Activa el escenario.
- [ ] **26.** Manda un POST a la URL del webhook (con Postman, curl o un formulario simple) con este JSON:
```json
{
  "nombre": "Test Lead",
  "email": "tu-email-de-prueba@gmail.com",
  "empresa": "Empresa Test SA",
  "mensaje": "Hola, quiero saber más sobre la Auditoría ACA",
  "origen": "Test manual",
  "urgencia": "caliente"
}
```
- [ ] **27.** ✅ En **menos de 1 min**: debe aparecer una fila nueva en Notion `Handoffs A2A`.
- [ ] **28.** ✅ En **menos de 1 min**: debe llegar un email de notificación al owner Blum (revisa también el CC de la CEO).
- [ ] **29.** ✅ En **menos de 2 min**: debe llegar el email de acuse a `tu-email-de-prueba@gmail.com` desde MailerLite.
- [ ] **30.** ✅ En Drive `AI-HQ/Pipeline/Handoffs/R1-Sonia-Blum/2026-05/`: debe existir un archivo JSON con el handoff completo.
- [ ] **31.** Abre la fila Notion → cambia el estado a `En curso`.

---

## Fase 6 — Test 2: SLA vencido (espera 4h)

- [ ] **32.** Manda otro POST al webhook con `urgencia=caliente` (mismo JSON, otro email de prueba).
- [ ] **33.** **NO toques Notion.**
- [ ] **34.** Espera 4 horas (o cambia temporalmente `SLA_HORAS_CALIENTE = 0.05` para probar en 3 minutos — pero **devuélvelo a 4 después**).
- [ ] **35.** ✅ Debe llegar email de alerta a la CEO.
- [ ] **36.** ✅ El estado en Notion debe haber cambiado a `Vencido N1 - escalado N2`.

---

## Fase 7 — Hardening (10 min)

- [ ] **37.** Revisa los logs de Make → ¿algún warning de seguridad? Si sí, regístralo en `seguridad/incidentes/`.
- [ ] **38.** Confirma que las connections están guardadas con scope mínimo (Drive: solo carpeta AI-HQ; Notion: solo base Handoffs).
- [ ] **39.** Activa 2FA en Make si no lo tienes ya.
- [ ] **40.** Programa rotación de claves API: 90 días.

---

## Fase 8 — Producción

- [ ] **41.** Borra los registros de prueba en Notion (o márcalos como `Descartado · prueba`).
- [ ] **42.** Conecta el webhook real a tu landing/podcast/LinkedIn de Sonia (formularios, Linktree, footer del podcast).
- [ ] **43.** Avisa al owner Blum N1 que está activo.
- [ ] **44.** Programa la primera auditoría mensual del log (`Pipeline/Logs/2026-05-handoffs-mensual.xlsx`) para el primer lunes del mes.
- [ ] **45.** ✅ R1 está en producción.

---

## Si algo falla

- **Webhook no recibe**: verifica que la URL es la correcta y que el escenario está activo.
- **Notion no crea fila**: revisa que el integration token tiene acceso a la base + que los nombres de las propiedades coinciden exactos.
- **MailerLite no manda acuse**: revisa que el grupo `blum-leads-r1` está bien escrito y que la automation está activa.
- **Email interno no llega**: revisa SMTP credentials + que el email del owner es válido.
- **Drive no sube archivo**: revisa permisos de la carpeta + scope del token.

Si nada funciona después de 30 min de troubleshooting → para, aplica `skills/seguridad/respuesta-incidentes.md` (no es seguridad, pero el runbook ayuda) y avísame.

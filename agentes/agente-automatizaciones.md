# ⚙️ agente-automatizaciones

## Rol
Infra técnica de la agencia: WAHA (WhatsApp HTTP API), Make.com, Notion, Drive, conectores con LLMs. Mantiene los flujos vivos y monitoriza fallas.

## Stack actual
- **WAHA** en Railway (WhatsApp gateway)
- **Make.com** (orquestación)
- **Notion** (CRM de clientes)
- **Drive workspace** `soniayanezblum@gmail.com` (almacenamiento)
- **Claude / OpenAI** (clasificación, redacción, resúmenes)
- **GitHub** (este repo)

## Escenarios Make planificados (3 a desplegar viernes)

### Esc.1 — WhatsApp inbox → Notion CRM
Trigger: webhook WAHA (mensaje entrante)
→ clasificador IA (lead / cliente / spam / urgente)
→ create/update fila en Notion CRM
→ si "urgente" → notificación push a Sonia.

### Esc.2 — Email cliente → resumen ACA → Drive
Trigger: email entrante con etiqueta `cliente:*`
→ resumen IA en formato ACA (3 atributos clave)
→ guardar en `Drive/Clientes/{nombre}/correos/`
→ enlace al CRM Notion.

### Esc.3 — Mención medios → alerta Reputación Algorítmica
Trigger: Google Alerts + búsqueda IA (3 prompts/cliente)
→ análisis de sentimiento + atributo ACA afectado
→ si negativo o >70% impacto → alerta Sonia + entrada en Notion.

## Outputs (artefactos)
- `infraestructura/waha-railway/` (docker-compose, railway.json)
- `infraestructura/make/escenario-1-whatsapp.json` (TODO)
- `infraestructura/make/escenario-2-email.json` (TODO)
- `infraestructura/make/escenario-3-menciones.json` (TODO)

## Reglas
- **Secretos nunca al repo.** Variables sensibles en `.env` local + Railway/Make secrets.
- Cada escenario lleva trigger de error → log a Notion.
- Health-checks diarios automatizados (cron Railway).
- Versionar cambios mayores con tag (v1, v2...).

## Checklist viernes 9:30
1. [ ] WAHA desplegado en Railway con QR escaneado.
2. [ ] Webhook URL pública (Railway domain).
3. [ ] Esc.1 importado y conectado al webhook.
4. [ ] Esc.2 importado con label gmail configurado.
5. [ ] Esc.3 importado con prompts ACA cargados.
6. [ ] Test end-to-end (mensaje de prueba → fila en Notion).

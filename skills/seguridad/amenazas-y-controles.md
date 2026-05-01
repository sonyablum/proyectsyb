# 🎯 Amenazas y controles — matriz por activo

> Mapa operativo: por cada activo crítico, qué amenaza esperar y qué control aplicar.

## Activos × amenazas × controles

### 1. WAHA (WhatsApp gateway en Railway)

| Amenaza | Control |
|---|---|
| Hijack del endpoint para envío de spam/scam | `WAHA_API_KEY` larga (≥ 64 chars) generada con `openssl rand -hex 32`. Rotar cada 90 días |
| Acceso al dashboard | `WAHA_DASHBOARD_PASSWORD` fuerte + IP allowlist si Railway lo permite |
| Webhook abierto a cualquier IP | Filtrar por IPs de Make.com en variable de entorno o reverse proxy |
| Robo de sesión WhatsApp del número | Volumen Railway persistente + alerta si la sesión cambia de "WORKING" a "SCAN_QR_CODE" inesperadamente |
| Mensajes filtrados con datos de clientes | Encriptar Notion CRM en reposo. Logs WAHA NUNCA al repo |

### 2. Make.com (orquestación)

| Amenaza | Control |
|---|---|
| Credenciales en blueprints exportados | Antes de exportar / compartir blueprints, verificar que `connection IDs` no expongan tokens |
| Webhooks expuestos abiertos | Cada webhook con clave secreta en query string + validación en el primer módulo |
| Errores que filtran datos | Trigger de error → registro en Notion con datos enmascarados, no el payload completo |
| Modificación no autorizada | 2FA en cuenta Make + revisar logs de cambios mensualmente |

### 3. Notion CRM

| Amenaza | Control |
|---|---|
| Acceso de invitado más amplio del necesario | Permisos por base de datos, no por workspace. Revisar mensual |
| Compartir página por error con link público | Auditoría mensual de "shared with web" en todas las páginas |
| Scraping vía API token expuesto | Token con scope mínimo, almacenado en Make/Railway secrets, rotación 90 días |
| Cliente Amcham / SFIC / UIDE ve datos de otro | Bases separadas o filtros por persona claramente probados |

### 4. Drive workspace `soniayanezblum@gmail.com`

| Amenaza | Control |
|---|---|
| ATO (account takeover) Gmail | 2FA con llave física (Yubikey) o app authenticator (no SMS). Recovery email de respaldo separado |
| Compartido público involuntario | Auditoría mensual de "anyone with link" en carpetas de clientes y de marco-aca |
| Borrado masivo (ransomware o accidental) | Backup semanal externo (rsync a disco externo o Backblaze) + papelera 30 días |
| Filtración de borradores académicos | Carpetas `marco-aca/` y `Delphi-R*/` con permiso restrictivo a Sonia + 2 colaboradores máximo |

### 5. Web Blum Digital PR + chat IA "Sofía"

| Amenaza | Control |
|---|---|
| Prompt injection en chat | Ver `prompt-injection-y-scraping.md` § Sofía |
| Scraping del contenido y de los DOIs | `robots.txt` permisivo solo a buscadores legítimos · rate limiting · Cloudflare Bot Fight |
| Inyección de scripts (XSS) | Sanitizar todo input de formularios · CSP restrictivo |
| Suplantación de dominio | Registrar dominios típicamente confundibles (.co, .es, ar, mx) si presupuesto permite |
| Robo de credenciales de la web | 2FA en hosting · admin panel con IP allowlist |

### 6. Email y comunicaciones académicas

| Amenaza | Control |
|---|---|
| Phishing dirigido a Sonia (spear phishing como Hase, congresos, editores) | Verificar siempre el dominio del remitente. Sospechar de adjuntos. Confirmar por canal alternativo si urge |
| Suplantación de Sonia hacia clientes | SPF + DKIM + DMARC configurados en dominio Blum · firma estándar |
| Filtración de borradores en email | NUNCA enviar borradores no autorizados a destinatarios académicos sin revisión CEO |

### 7. Repositorios GitHub

| Amenaza | Control |
|---|---|
| Secretos commiteados por accidente | `.gitignore` cubre `.env*` · pre-commit hook con `gitleaks` o equivalente |
| Branch `main` sobre-escrito | Rama protegida con PR review required |
| Token GitHub robado | Personal Access Tokens con scope mínimo · rotación 90 días |

### 8. Plataformas de pago (Stripe, BBVA, PayPal)

| Amenaza | Control |
|---|---|
| ATO de cuenta de pago | 2FA físico · alertas de transacción al teléfono · revisión semanal |
| Stripe keys filtradas | Solo en backend / secrets · rotación inmediata si sospecha |
| Sonja Kalos comparte cuenta de pago con otras marcas | Cuenta Stripe **separada** para Sonja Kalos cuando arranque (firewall) |

### 9. ORCID + Zenodo (identidad académica)

| Amenaza | Control |
|---|---|
| ATO ORCID | 2FA + recovery email separado |
| Subida indebida a Zenodo (borrador no autorizado) | Solo Sonia sube. El Jefe de Despacho **nunca** ejecuta deposit sin OK escrito |
| Cita externa de DOIs no públicos | Auditoría mensual de menciones de "ACA-Score v3", "FACE", "GEAC", "ACA Seal" en Google + Perplexity + ChatGPT |

### 10. Repositorio de prompts y skills

| Amenaza | Control |
|---|---|
| Filtración de prompts curados Sonja Kalos al universo Sonia/Blum/ARP | Carpeta `marcas/sonja-kalos/operativa/` aislada con regla "ningún archivo cruza dominios" |
| Robo de prompts del Marco ACA / RICFE | Mantener solo versiones públicas en repos accesibles · versiones extendidas en privado |

## Hardening básico esta semana (acción Sprint 1)

- [ ] 2FA con app (no SMS) en: Gmail · Drive · Notion · Make · Railway · GitHub · ORCID · Zenodo · BBVA · PayPal
- [ ] `.gitignore` revisado · pre-commit hook `gitleaks` instalado en repo principal
- [ ] WAHA `WAHA_API_KEY` rotada y guardada en password manager
- [ ] Auditoría inicial de "shared with anyone" en Drive
- [ ] Recovery email separado configurado para Gmail principal
- [ ] Backup externo del repo + Drive crítico configurado (semanal)

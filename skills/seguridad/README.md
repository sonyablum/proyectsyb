# 🛡 Seguridad — Grupo Sonia Yánez Blum

> Capa de defensa transversal a las 4 marcas. Aplica a infraestructura, datos, identidades digitales, IAs operativas y firewall Sonja Kalos.

## Modelo de amenazas

**Qué protegemos**:
1. Activos intelectuales no publicados (ACA-Score v3, FACE Working Paper, Protocolo GEAC, ACA Seal, datos Delphi).
2. Datos de clientes externos (Amcham, SFIC, UIDE) y sus mensajes WhatsApp.
3. Datos de alumnos Academia ARP y suscriptores Sonja Kalos (sensibles GDPR).
4. Infraestructura técnica (WAHA, Make, Notion, Drive, web Blum + chat Sofía).
5. Identidad académica de Sonia (ORCID, DOIs, reputación algorítmica de la propia Sonia).
6. **Firewall Sonja Kalos** — separación absoluta narrativa, visual y técnica.

**De quién**:
- Bots de scraping (extraen contenido + datos de clientes/alumnos).
- Atacantes de prompt injection contra chats IA y los Presidentes IA.
- Hackers que buscan ATO (account takeover) de Gmail / Drive / Make / WAHA.
- Phishing / suplantación de Sonia o de las marcas.
- Robadores de PI académica (preprints, datos Delphi).
- Filtraciones internas (cruce accidental Sonja Kalos ↔ otras marcas).
- Malware en el ordenador de Sonia o colaboradores.

## 5 capas de defensa

| Capa | Foco | Skill |
|---|---|---|
| 1. **Identidades y accesos** | 2FA, gestión de secretos, mínimo privilegio | `seguridad/amenazas-y-controles.md` |
| 2. **Datos sensibles** | GDPR, anonimización, retención, consentimiento | `seguridad/datos-sensibles-gdpr.md` |
| 3. **IAs operativas** | Anti-prompt-injection, anti-scraping, anti-jailbreak | `seguridad/prompt-injection-y-scraping.md` |
| 4. **Firewall Sonja Kalos** | Aislamiento técnico digital + narrativo | `seguridad/firewall-sonja-kalos-tecnico.md` |
| 5. **Respuesta a incidentes** | Runbook 4 horas + comunicación + forensía | `seguridad/respuesta-incidentes.md` |

## Reglas inquebrantables de seguridad

1. ⛔ **Secretos nunca al repo** (`.env`, claves API, contraseñas). Usar Railway / Make / 1Password equivalente.
2. ⛔ **2FA obligatorio** en: Gmail Sonia, Drive workspace, Notion, Make, Railway, GitHub, ORCID, Zenodo, BBVA, PayPal, Stripe.
3. ⛔ **Ningún dato de cliente externo** en piezas públicas sin consentimiento por escrito.
4. ⛔ **Ningún dato de panelista Delphi** identificado individualmente — solo agregados.
5. ⛔ **Ningún cruce Sonja Kalos ↔ otras marcas** en metadatos, autores, dominios, IPs públicas, emails, plataformas de pago.
6. ⛔ **Ningún chat IA** (Sofía, Presidentes IA) ejecuta acciones con efectos externos sin OK humano.
7. ⛔ **Ningún email a Hase / academia / clientes** se envía sin OK explícito de la CEO.
8. ✅ **Backup semanal** del repo + Drive crítico + base Notion CRM.
9. ✅ **Rotación trimestral** de claves API y contraseñas críticas.
10. ✅ **Auditoría mensual** de accesos y permisos en cada plataforma.

## Responsables

| Quién | Qué |
|---|---|
| **CEO (Sonia)** | Autoriza cambios estructurales · firma envíos externos · decide sobre incidentes mayores |
| **Jefe de Despacho** | Vigila las 5 capas · ejecuta runbook · entrega reporte mensual de seguridad |
| **Pdte. Blum** | Seguridad de WAHA, Make, Notion CRM, datos cliente, web + chat Sofía |
| **Pdte. Sonia Yánez** | Seguridad de ORCID, Zenodo, datos panelistas Delphi, comunicación con Hase |
| **Pdte. Academia ARP** | Seguridad de plataforma cursos, datos alumnos, e-commerce |
| **Pdte. Sonja Kalos** | Seguridad del silo + integridad firewall técnico |

## Cuándo invocar cada skill

| Situación | Skill primaria |
|---|---|
| Antes de desplegar / cambiar infra | `amenazas-y-controles.md` |
| Antes de procesar datos personales (Delphi, alumnos, suscriptores Sonja Kalos) | `datos-sensibles-gdpr.md` |
| Antes de exponer un chat IA público o conectar API | `prompt-injection-y-scraping.md` |
| Antes de cualquier comunicación o pieza Sonja Kalos | `firewall-sonja-kalos-tecnico.md` |
| Cuando se sospecha un incidente | `respuesta-incidentes.md` (los primeros 60 minutos cuentan) |

## Auditoría mensual mínima

- [ ] Revisar lista de accesos en cada plataforma (quién tiene acceso, con qué permisos, hace cuánto).
- [ ] Revisar logs de Make, WAHA, Notion (intentos fallidos, IP raras).
- [ ] Buscar menciones nuevas de Sonja Kalos cruzando con Sonia / Blum / ARP (Google, Bing, ChatGPT, Perplexity).
- [ ] Confirmar que las 3 reglas duras anti-canibalización no se hayan violado.
- [ ] Confirmar que ningún DOI no autorizado se haya citado externamente.
- [ ] Test rápido de prompt injection en chat Sofía.
- [ ] Backups del mes verificados (no solo creados — restaurables).

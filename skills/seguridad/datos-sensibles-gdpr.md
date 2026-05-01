# 🔐 Datos sensibles y GDPR — protección por tipo de dato

> Sonia reside en Austria → GDPR aplica. Clientes y alumnos en LATAM/España añaden sus propias leyes (LOPD España, leyes de protección de datos en Ecuador, México, Colombia, Argentina).

## Clasificación de datos por sensibilidad

| Nivel | Tipo de dato | Ejemplos en el grupo |
|---|---|---|
| **🔴 Crítico** | Categoría especial GDPR · datos identificables que pueden causar daño | Suscriptores Sonja Kalos (esotérico = creencias/salud mental) · respuestas individuales del Delphi · contenido de WhatsApp Amcham · datos financieros |
| **🟠 Alto** | Datos personales identificables comunes | Email + nombre de alumnos ARP · contactos de clientes Blum · contactos académicos · CVs |
| **🟡 Medio** | Datos pseudonimizados o profesionales | Métricas agregadas Delphi · KPIs por cuenta · monitoreo de menciones |
| **🟢 Bajo** | Datos públicos | DOIs Zenodo · ORCID público · contenido de marketing publicado |

## Reglas por tipo

### 🔴 Sonja Kalos — suscriptores y consultas esotéricas

- **Consentimiento**: explícito, granular, revocable. Texto del disclaimer AI obligatorio.
- **Almacenamiento**: cuenta SaaS independiente (no Notion del grupo). Encriptación en reposo.
- **Retención**: máximo 24 meses tras última interacción. Borrado completo a petición en 30 días.
- **Cruces**: cero. No se exporta a Drive del grupo, no a Notion del grupo.
- **Logs**: anonimizados después de 90 días.

### 🔴 Delphi (panelistas)

- **Consentimiento**: firmado al inicio de cada ronda. Texto incluye: uso académico, anonimización agregada, derecho a retirarse.
- **Almacenamiento**: Sheet en Drive con permiso restrictivo. Idealmente con columna ID interna y diccionario maestro separado.
- **Reportes públicos**: solo distribuciones agregadas (% consenso, M, SD). NUNCA respuestas individuales identificables.
- **Borrado**: a petición → eliminar fila + actualizar análisis.

### 🔴 WhatsApp Amcham (8 chats activos)

- **Base legal**: contrato comercial activo + consentimiento implícito por el canal.
- **Almacenamiento**: WAHA en Railway con encriptación de volumen. Backups encriptados.
- **Acceso**: solo Sonia + Pdte. Blum + subagente-pr-medios. NUNCA exportar texto a archivos planos sin OK CEO.
- **Retención**: 24 meses post-fin del contrato.

### 🟠 Alumnos Academia ARP

- **Consentimiento**: checkbox al registrarse + política de privacidad enlazada.
- **Almacenamiento**: plataforma de cursos elegida (verificar GDPR-compliant) + email marketing tool.
- **Marketing**: solo a quien optó in. Unsubscribe en cada email.
- **Cruces**: si un alumno califica para upsell a Blum (R6 A2A), el handoff lleva consentimiento explícito o se le pregunta antes.

### 🟠 Contactos clientes Blum (SFIC, UIDE, otros)

- **Almacenamiento**: Notion CRM con permisos restrictivos.
- **Compartir con terceros**: nunca sin OK del cliente.
- **Casos de éxito públicos**: SOLO anonimizados, nunca con nombre del cliente sin contrato firmado de uso.

### 🟠 Contactos académicos (Hase, congresos, editores)

- **Trato**: profesional + privado. Nunca añadir a listas de marketing.
- **Email**: usar canal académico de Sonia, no canal Blum.

## Derechos GDPR a soportar

Para cualquier dato personal en el grupo, los siguientes derechos deben estar disponibles:

- ✅ **Acceso**: la persona puede pedir copia de sus datos.
- ✅ **Rectificación**: puede corregirlos.
- ✅ **Supresión**: "derecho al olvido" — borrado dentro de 30 días.
- ✅ **Limitación**: pausar el uso de sus datos.
- ✅ **Portabilidad**: exportar sus datos en formato legible.
- ✅ **Oposición**: rechazar uso para marketing.

**Email único de contacto** para ejercer derechos: `soniayanezblum@gmail.com` (o el que se publique formalmente). Plazo de respuesta legal: 30 días.

## Política de retención (resumen)

| Dato | Retención |
|---|---|
| WhatsApp Amcham | 24 meses post-contrato |
| Email cliente Blum | 36 meses post-última actividad |
| Alumnos ARP inactivos | 24 meses post-última actividad → anonimización |
| Suscriptores Sonja Kalos | 24 meses post-última interacción |
| Delphi panelistas | 7 años (estándar académico) — solo agregados; identificables 24 meses |
| Borradores académicos | Indefinido (interno) |
| Logs técnicos (WAHA, Make) | 12 meses, después anonimizados |

## Procesadores externos (data processing agreements)

Verificar que cada plataforma usada haya firmado o publique DPA conforme GDPR:

- ✅ Google Workspace (DPA estándar)
- ✅ Make.com (DPA estándar)
- ✅ Railway (verificar)
- ✅ Notion (DPA estándar)
- ✅ Stripe / PayPal / BBVA (legalmente regulados)
- 🟡 Plataforma cursos elegida → verificar antes de contratar
- 🟡 Plataforma esotérica Sonja Kalos → verificar antes de lanzar

## Auditoría trimestral

- [ ] Revisar lista de procesadores externos · DPAs vigentes.
- [ ] Revisar política de privacidad publicada (al día).
- [ ] Test de "borrado a petición": simular request → verificar que se ejecuta dentro de 30 días.
- [ ] Verificar que ningún export reciente cruzó dominios (ej: alumno ARP en lista de Sonja Kalos).

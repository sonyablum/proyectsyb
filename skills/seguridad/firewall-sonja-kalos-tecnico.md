# 🛑 Firewall técnico Sonja Kalos

> Las reglas narrativas están en `marcas/sonja-kalos/README.md` y `gobernanza/anti-canibalizacion.md`. Aquí los controles **técnicos digitales** que evitan filtraciones por huellas SEO, metadatos, IPs, autores en posts, plataformas compartidas.

## Aislamiento técnico — checklist por capa

### Identidad digital
- [ ] **Dominio propio** independiente para Sonja Kalos. NO usar subdominio de Blum / Sonia / ARP.
- [ ] **Email del proyecto** en dominio propio (`hola@dominio-sonja-kalos.tld`). NUNCA `@soniayanezblum.com` ni @gmail.com personal.
- [ ] **WHOIS privado** del dominio para no filtrar registrante.
- [ ] **Marca registrada o no**: si se registra, usar entidad jurídica diferente o nombre distinto al de Sonia personal.

### Hosting e infraestructura
- [ ] **Hosting independiente** (no compartir cuenta de Vercel / Netlify / Railway con las otras marcas).
- [ ] **DNS y CDN** separados. Idealmente Cloudflare con cuenta dedicada al proyecto.
- [ ] **Cuenta Stripe** independiente cuando se acepten pagos. No compartir merchant ID.
- [ ] **Cuenta Google Analytics / Plausible** separada. Nunca property compartida con Blum/ARP/Sonia.
- [ ] **Mailing tool** separado (no MailerLite del grupo si se adopta para ARP).

### Contenido y metadatos
- [ ] **Autor en posts**: nunca "Sonia Yánez Blum". Usar el personaje "Sonja Kalos" o un alias creativo.
- [ ] **Metadatos de imagen** (EXIF): limpiar antes de subir cualquier imagen. EXIF puede contener author, GPS, software.
- [ ] **Documentos PDF/Word**: limpiar metadatos (author, last modified by) antes de publicar.
- [ ] **Schema.org / JSON-LD**: NO usar `Person` apuntando a Sonia. Usar `Organization` ficticia o `VirtualPerson` declarado.
- [ ] **Open Graph y Twitter Card**: revisar que no salga "Sonia Yánez Blum" como `og:author`.

### Disclaimer AI (transparencia obligatoria)
- [ ] **Disclaimer estándar** en footer de web, redes y emails:
  > "Sonja Kalos es una persona digital creada con inteligencia artificial. Ella no es humana."
- [ ] **Términos de servicio** declaran uso de IA.
- [ ] **Cookies y privacy policy** independientes.

### Redes sociales
- [ ] **Cuentas dedicadas** (Instagram, TikTok, X, etc.) con email del proyecto.
- [ ] **Bio**: declara entidad AI sin vínculo a Sonia.
- [ ] **Cross-promo prohibida**: nunca seguir / interactuar / mencionar las cuentas de Sonia / Blum / ARP desde Sonja Kalos (y viceversa).
- [ ] **Login**: nunca logueada simultáneamente en el mismo browser que las otras marcas (usa contenedores de Firefox o perfiles separados).

### Pagos
- [ ] **Stripe / Mercado Pago / Paddle** en cuenta separada.
- [ ] **Recibo al cliente** desde el alias del proyecto, no desde Sonia.
- [ ] **Cuenta bancaria** receptora puede ser la misma de Sonia (operativa fiscal individual), pero el detalle del recibo NUNCA expone "Sonia Yánez Blum".
- [ ] **Reportes financieros públicos** (si los hay): nunca consolidar Sonja Kalos con las otras marcas.

### Repositorio de código y prompts
- [ ] **Carpeta `marcas/sonja-kalos/operativa/`** en este repo está aislada por convención de archivos (ningún archivo cruza dominios).
- [ ] Si Sonja Kalos crece técnicamente → mover su operativa a un **repo privado independiente**, sin referencias a este repo del grupo.
- [ ] **Commits en este repo** nunca mezclan cambios Sonja Kalos con cambios de otras marcas (commits separados para auditoría limpia).

### IAs operativas
- [ ] **Pdte. Sonja Kalos** opera en sesiones separadas. Su prompt nunca recibe contexto de las otras 3 marcas.
- [ ] **Sub-agentes funcionales** (marketing, automatizaciones) que sirven a Sonja Kalos lo hacen en sesiones aisladas.
- [ ] **Plantillas y prompts** específicos del silo viven solo en la operativa Sonja Kalos.

## Auditoría mensual del firewall

Ejecutar el primer lunes de cada mes:

### Cruzado SEO (huella digital)
1. **Google**: `"Sonja Kalos" "Sonia Yánez"` → debe dar **0 resultados**.
2. **Google**: `"Sonja Kalos" Blum` → debe dar **0 resultados**.
3. **Google**: `"Sonja Kalos" ACA-Score` → debe dar **0 resultados**.
4. **ChatGPT / Claude / Perplexity / Gemini**: preguntar "¿Quién es Sonja Kalos?" y "¿Quién está detrás de Sonja Kalos?" → ninguna respuesta debe apuntar a Sonia o al grupo.

### Cruzado técnico
1. WHOIS del dominio Sonja Kalos → registrante NO debe ser Sonia.
2. Headers HTTP del sitio Sonja Kalos → ningún `X-Powered-By` o cookie compartida con dominios del grupo.
3. Reverse IP lookup → NO debe compartir IP con web de Blum / ARP / Sonia personal.
4. EXIF de últimas 5 imágenes publicadas → limpio.
5. Metadatos de últimos 5 PDF / docs publicados → limpio.

### Cruzado humano
1. Ningún post de Sonia / Blum / ARP en los últimos 30 días menciona Sonja Kalos.
2. Ningún post de Sonja Kalos en los últimos 30 días menciona Sonia / Blum / ARP.
3. Cuentas RRSS de Sonja Kalos NO siguen ni son seguidas por las cuentas de las otras marcas.

### Si una verificación falla
1. **Pausar** publicaciones públicas en la marca afectada.
2. **Documentar** la fuga (captura, URL, fecha).
3. **Limpiar** la fuga (request de removal a Google, edit, eliminar post, etc.).
4. **Notificar** a la CEO inmediatamente.
5. **Causa raíz**: revisar qué control falló y endurecer.

## Lo que NUNCA pasa por el repo principal

Aunque la operativa Sonja Kalos esté en `marcas/sonja-kalos/operativa/`:
- ❌ Ningún password / API key del proyecto Sonja Kalos.
- ❌ Ningún dato real de suscriptores Sonja Kalos.
- ❌ Ningún test público del personaje (capturas, drafts) sin disclaimer.
- ❌ Cualquier commit que menciona Sonja Kalos no debe incluir cambios de otras marcas en el mismo commit (auditoría limpia).

# Landing Auditoría ACA™ — Especificación de diseño y copy

> Spec para `blumdigitalpr.com/auditoria` (nueva página) o rehacer homepage.
> 6-nov-2026 · Jefe de Despacho.

## Objetivo único

Convertir visitante B2B en comprador de uno de los 3 SKU Blum, sin intervención manual de Sonia.

## Estructura de la página (en orden de scroll)

### Sección 1 — Hero (sobre el fold)

**H1**: La IA ya está decidiendo qué dice de tu organización.

**H2 (subtítulo)**: Auditamos qué están diciendo ChatGPT, Claude, Gemini y Perplexity sobre tu marca, y te damos el plan para corregirlo. Marco ACA™, por Sonia Yánez Blum.

**CTA primario**: `Elegir mi auditoría` → scroll a sección de pricing.

**CTA secundario**: `Ver cómo funciona` → scroll a sección metodología.

**Visual**: captura real (sin nombres de cliente) de un reporte ACA-Score mostrando los 4 cuadrantes del marco.

### Sección 2 — Prueba de autoridad

> "El Marco ACA™ es el primer sistema de auditoría de reputación en modelos de IA generativa publicado en el ámbito académico hispano."

Trust marks:
- Autora del Marco ACA™ · ACA-Score™ · RICFE®
- +28 años en comunicación estratégica
- Investigadora independiente · ORCID 0000-0002-6695-8129
- Ponente UOC Barcelona · conferencias LATAM
- Preprints Zenodo con DOI público

Logos de confianza: Amcham Guayaquil · SFIC · UIDE *(verificar autorización de uso)*

### Sección 3 — Los 3 servicios (precios visibles)

Tabla / cards lado a lado:

| | **Express** | **Professional** | **Retención** |
|---|---|---|---|
| Precio | **$497 USD** | **$1.200 USD** | **$1.500 USD / mes** |
| Entrega | 5 días hábiles | 15 días hábiles | Continuo |
| Reporte ACA-Score | ✅ | ✅ | ✅ trimestral |
| Acciones priorizadas | 5 | Plan 90 días | 4/mes |
| Sesiones 60 min | 1 | 3 | 1/mes |
| Monitoreo continuo | — | — | ✅ |
| Para quién | Freelancers · pymes · personas | Agencias · ejecutivos · marcas medianas | Empresas que quieren control continuo |
| | [Comprar Express](https://buy.stripe.com/aFa7sF1yfa7scSjgvRc3m0g) | [Comprar Professional](https://buy.stripe.com/aFa00d90HgvQ7xZ93pc3m0h) | [Suscribirme](https://buy.stripe.com/9B69ANa4LcfA4lNgvRc3m0i) |

### Sección 4 — Cómo funciona (metodología)

4 pasos visuales:

1. **Pagas por Stripe**. En menos de 60 segundos.
2. **Recibes el intake** en 24 h hábiles. 10 preguntas sobre tu entidad.
3. **Auditamos** tu presencia en ChatGPT, Claude, Gemini, Perplexity con el Marco ACA™.
4. **Recibes el reporte** con tu ACA-Score y las acciones priorizadas. Más sesión en vivo con Sonia.

### Sección 5 — Qué entregamos exactamente

**Para Express ($497)**:
- PDF ejecutivo (10–15 páginas) con:
  - Tu ACA-Score inicial (A, C, A — Autoridad, Coherencia, Amplificación)
  - 5 acciones priorizadas con impacto esperado
- Sesión 60 min por Zoom con Sonia Yánez Blum

**Para Professional ($1.200)**:
- Todo lo del Express
- Plan 90 días: hoja de ruta detallada por mes
- 3 sesiones 60 min (día 1, día 45, día 90)
- Análisis cruzado con fuentes citables y cobertura de medios

**Para Retención ($1.500/mes)**:
- Monitoreo mensual del ACA-Score (comparativo)
- 4 entregables/mes (post, respuesta a mención, nota de prensa, resumen ejecutivo)
- Sesión mensual 60 min
- Reporte ACA™ trimestral completo
- Compromiso mínimo: 3 meses. Cancelación libre desde el mes 4.

### Sección 6 — Testimonios

3 citas reales (pedir a Sonia):
- Cita Amcham Guayaquil
- Cita SFIC
- Cita UIDE

Formato: foto · nombre · cargo · empresa · cita 2–3 líneas.

Si al momento de publicar no hay citas autorizadas, usar **sección "Logros públicos"** en vez de testimonios:
- Preprints con DOI Zenodo
- Charla UOC Barcelona abril 2026
- Columnista El Universo
- Fundadora Academia ARP (2020)

### Sección 7 — FAQ

Preguntas que importan:
1. ¿Cómo sé que funciona? → cita 1 caso + preprint Zenodo
2. ¿Qué pasa si mi ACA-Score es bajo? → "ese es el punto. Te damos las acciones"
3. ¿Necesito dar accesos internos? → "no. Trabajamos con fuentes públicas"
4. ¿En qué idiomas? → español
5. ¿Facturación? → Stripe genera factura automática. Austria/Ecuador según sede fiscal de Sonia
6. ¿Garantía? → 7 días para cambio por mismo valor. Sin reembolso tras entrega del reporte

### Sección 8 — Última llamada

**H3**: ¿Qué estás esperando?

**Texto corto**: Cada semana sin medición es una semana en que la IA está construyendo tu reputación sin tu criterio.

**3 botones** (los mismos de la sección 3).

### Footer

- Blum Digital PR · info@blumdigitalpr.com
- Firewall legal: Marco ACA™, ACA-Score™, RICFE® son propiedad intelectual de Sonia Yánez Blum, licenciados a Blum Digital PR y Academia de Relaciones Públicas ARP.
- Sin cross-link a Sonja Kalos.

## Elementos técnicos

- **Stack**: lo que ya hay (WordPress o Framer). Si es WordPress, usar Elementor con los 3 payment link buttons.
- **Favicon y meta**: `Blum Digital PR — Auditoría de Reputación Algorítmica`.
- **Open Graph**: imagen con "ACA-Score · Marco de Auditoría de Reputación Algorítmica".
- **Schema.org**: `Service` con `offers` para cada SKU. Mejora GEO/AEO en buscadores de IA.
- **Chat SofIA**: cambiar prompt del chat para calificar lead (nombre, email, qué marca, tamaño) → push a MailerLite grupo "Blum lead cualificado".

## Checklist antes de publicar

- [ ] Las 3 URLs de Stripe funcionan (verificadas 6-nov-2026 ✅).
- [ ] Testimonios con autorización escrita.
- [ ] Logos de clientes con autorización escrita.
- [ ] Términos y Condiciones + Política de Privacidad enlazados en footer.
- [ ] Pixel de analytics (GA4 o Plausible) instalado.
- [ ] GSC verificado.
- [ ] Schema markup validado en validator.schema.org.
- [ ] Eliminar o redirigir la página vieja `/diagnostico-aca` a `/auditoria` (301).
- [ ] Revisión final de Sonia.

## Qué falta de Sonia

1. 3 testimonios con autorización.
2. Logos de clientes con autorización (Amcham, SFIC, UIDE).
3. Confirmar quién implementa (ella, developer externo, Jefe deja HTML listo).

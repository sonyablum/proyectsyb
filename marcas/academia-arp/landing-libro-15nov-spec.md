# Landing preventa libro "Reputación Algorítmica" — 15-nov-2026

> Spec urgente. 9 días de ventana. 6-nov-2026 · Jefe de Despacho.
> Stripe product: `prod_VTKRkYLzSXl0Gn` · ebook digital PDF.

## Objetivo

Vender 100 preventas del libro en 9 días (6-nov → 15-nov).

## Estado actual

- ✅ Producto Stripe existe (ebook, preventa).
- 🔴 **Precio por confirmar**: el producto Stripe no tiene `default_price` cargado. Hay que fijarlo antes de activar landing.
- 🔴 El libro NO está en la home de academiaderelacionespublicas.com.
- 🔴 No hay página dedicada.

## Precio sugerido (decisión de Sonia)

- **Preventa (hasta 15-nov)**: $19 USD.
- **Precio regular (desde 16-nov)**: $29 USD.
- Lógica: descuento del 34% por preventa + urgencia clara.
- *Si Sonia prefiere otro precio, lo cambiamos en Stripe en 1 minuto.*

## Estructura de la landing `/libro`

### Sección 1 — Hero con countdown

**H1**: Reputación Algorítmica: la nueva frontera en RRPP.

**Subtítulo**: Edición digital por Sonia Yánez Blum. Entrega el 15 de noviembre de 2026.

**Elementos visuales**:
- Portada del libro (imagen 3D del PDF).
- Countdown "faltan X días para el lanzamiento".
- Precio tachado $29 · Precio preventa **$19** · Ahorro 34%.

**CTA primario**: `Comprar ahora en preventa — $19` → Stripe Payment Link.

### Sección 2 — Qué es este libro

**Resumen 3 líneas**:
Un libro sobre cómo se forma la reputación de personas y organizaciones en los sistemas de IA generativa y en los buscadores. Dirigido a profesionales de comunicación y relaciones públicas. Primera edición digital en español.

### Sección 3 — Índice / qué incluye

- Introducción: la crisis de autoridad en la era de la IA generativa
- Capítulo 1: qué es la reputación algorítmica
- Capítulo 2: cómo nos leen los LLMs
- Capítulo 3: el Marco ACA™ (Autoridad · Coherencia · Amplificación)
- Capítulo 4: medir con el ACA-Score™
- Capítulo 5: 5 estrategias de intervención (GEO)
- Capítulo 6: ética algorítmica en comunicación corporativa
- Caso de estudio: 3 auditorías reales anonimizadas
- Apéndice: 20 prompts RICFE® aplicados

*(Sonia debe confirmar el índice real del libro)*

### Sección 4 — Para quién es

Lista corta:
- DirCom y Head of Communications
- Agencias de PR y consultoras
- Profesores de comunicación
- Comunicadores independientes
- Estudiantes de últimos semestres

### Sección 5 — Sobre la autora

Foto + bio corta de Sonia:
- Especialista en RRPP 6.0 e IA, autora del Marco ACA™
- +28 años en comunicación estratégica
- Investigadora independiente · ORCID 0000-0002-6695-8129
- Ponente UOC Barcelona
- Fundadora Academia ARP y Blum Digital PR

### Sección 6 — FAQ

1. ¿Cuándo recibo el libro? → El 15-nov-2026 por email.
2. ¿Qué formato? → PDF digital. No hay versión impresa.
3. ¿Puedo imprimirlo? → Sí, para uso personal. No puede redistribuirse.
4. ¿Pago seguro? → Sí, por Stripe.
5. ¿Factura? → Automática desde Stripe.
6. ¿Garantía? → 7 días para cambio por otro producto de ARP de igual valor. Sin reembolso tras entrega del PDF.

### Sección 7 — Última llamada con countdown

Repetir el countdown + CTA.

Subtexto: "Después del 15-nov sube a $29".

## Secuencia email (preventa)

Crear en MailerLite, disparar a:
- Todo el grupo de Maratón 2026 (810 suscriptores previos)
- Grupo general ARP activos
- Suscriptores RICFE (ya compraron)

| Fecha | Asunto | Objetivo |
|---|---|---|
| **lun 7-nov** | Lo que la IA dice de ti (y por qué deberías saberlo antes del 15-nov) | Anuncio preventa |
| **mié 9-nov** | 3 páginas del capítulo 3 (preview) | Prueba de valor |
| **vie 11-nov** | Quedan 4 días a $19 | Urgencia |
| **sáb 14-nov** | Última llamada: mañana sube a $29 | Cierre |
| **dom 15-nov** | ¡Tu libro está en tu bandeja! | Entrega |

## Cross-sell en checkout

En el Payment Link del libro, añadir:
- Upsell visual post-compra: "¿Quieres aplicar lo que leíste? Agenda tu Auditoría ACA™ Express por $497" → link a Blum.
- Después de la compra, trigger automation "ARP libro → candidato Express" en MailerLite.

## Qué falta de Sonia (decidir hoy)

1. **Precio preventa** → ¿$19 confirmado o diferente?
2. **Portada final** del libro (imagen).
3. **Índice real** del libro.
4. **Foto autor** si no está ya en la web.
5. **Confirmación**: ¿la entrega del PDF es manual el 15-nov, o automática por MailerLite trigger?

# Journey comercial del grupo — mapa corregido

> Diagnóstico y diseño por Jefe de Despacho. 6-nov-2026.
> Base: auditoría Stripe (12 productos ARP + 3 nuevos Blum + Maratón), MailerLite (50+ automations), webs de las 3 marcas públicas, repo.

## 1. Journey actual (como está hoy)

```
  Descubrimiento           Consideración           Conversión            Onboarding            Expansión
  ─────────────           ─────────────           ──────────            ──────────            ──────────

LinkedIn ──┐
Medios ────┤
Podcasts ──┤─► soniayanez.com ──► form "colaboración académica" ──► correo manual ──► ??
Boca-oreja ┘        │
                    │ cross-link
                    ▼
            blumdigitalpr.com ──► "Diagnóstico ACA" sin precio ──► form contacto ──► correo manual Sonia ──► propuesta manual ──► cierre manual
                    │
                    │ (no hay cross-link claro)
                    ▼
       academiaderelacionespublicas.com ──► cursos listados ──► info page ──► ??? ──► (pocos llegan a checkout)
                    │
                    ▼
                 Maratón ──► payment link Stripe directo ──► $15/$25 ──► ❌ sin upsell visible
```

**Puntos de fuga identificados**:
- Blum: 100% manual. No convierte sin intervención de Sonia.
- ARP: cards sin checkout directo pierden conversión.
- Maratón: 1.000+ compradores sin oferta de upsell visible.
- soniayanez.com: contamina firewall académico/comercial.
- MailerLite: 4 secuencias Blum en draft (nunca encendidas).
- Naming inconsistente: "Diagnóstico ACA" (web) vs "Auditoría ACA™" (Stripe catálogo).

## 2. Journey corregido (target)

### Capa 1 — Descubrimiento

| Entrada | Destino | Función |
|---|---|---|
| Búsqueda "Sonia Yánez" | **soniayanez.com** | Autoridad académica pura. Zero tráfico a Blum/ARP sin propósito. |
| Búsqueda "auditoría IA reputación" | **blumdigitalpr.com** | Landing $497/$1.200/$1.500 con precios claros y checkout 1-clic. |
| Búsqueda "curso IA comunicación" | **academiaderelacionespublicas.com** | Catálogo B2C con libro 15-nov destacado + grabaciones Maratón. |
| Mención prensa / podcast | soniayanez.com + form prensa | Captura cualificada. |
| LinkedIn outbound (Apollo) | blumdigitalpr.com/auditoria | Lead cualificado → Express. |

### Capa 2 — Consideración

**Lead magnet universal**: `Playbook ACA — Reputación Algorítmica en 30 min` (PDF).
- Se ofrece en las 3 webs según contexto (académico, B2B, B2C).
- Captura: email → MailerLite con etiqueta de origen (`source: blum|arp|sonia`).
- Dispara nurture segmentado.

**Nurture Blum (5 emails)**:
1. E+0: Entrega Playbook ACA.
2. E+2: Caso Amcham/SFIC/UIDE (sin nombres si no autorizado).
3. E+5: Qué diferencia una Express de un "informe de IA" convencional.
4. E+8: Testimonial + CTA Express $497.
5. E+14: Breakup: "¿esto te toca este trimestre o cierro el ciclo?"

### Capa 3 — Conversión

| Producto | Marca | Entry point | Precio | Payment link |
|---|---|---|---|---|
| Auditoría ACA™ Express | Blum | blumdigitalpr.com/auditoria | $497 | https://buy.stripe.com/aFa7sF1yfa7scSjgvRc3m0g |
| Auditoría ACA™ Professional | Blum | blumdigitalpr.com/auditoria | $1.200 | https://buy.stripe.com/aFa00d90HgvQ7xZ93pc3m0h |
| Retención Mensual | Blum | blumdigitalpr.com/retencion | $1.500/mes | https://buy.stripe.com/9B69ANa4LcfA4lNgvRc3m0i |
| Libro Reputación Algorítmica | ARP | academiaderelacionespublicas.com/libro | $XX | (preventa 15-nov — precio por confirmar) |
| Pack RICFE | ARP | academiaderelacionespublicas.com/ricfe | $199 | https://buy.stripe.com/9B6dR390H4N85pR6Vhc3m03 |
| Nivel 1 + 2 Reputación | ARP | academiaderelacionespublicas.com/reputacion | $XX | https://buy.stripe.com/9B6bIV0ubdjE3hJenJc3m05 |

**Principio**: cada botón de "Comprar" **salta directo a Stripe Payment Link**. Sin pasos intermedios, sin login previo, sin form extra.

### Capa 4 — Onboarding

**Express ($497)**:
- T+0: Stripe confirmation → trigger MailerLite "ENTREGA — Intake Express"
- T+0: Email con Google Form de intake (10 preguntas + Calendly link)
- T+24h: Email "Tu intake se recibió, sesión agendada para [fecha]"
- T+5 días: Entrega del reporte ACA
- T+7 días: Sesión 60 min
- T+14 días: Email "¿cómo te fue? ¿siguiente paso Professional?"

**Professional ($1.200)**:
- Mismo flujo + 3 sesiones en 90 días
- T+45 días: Chequeo intermedio
- T+90 días: Upsell Retención

**Retención ($1.500/mes)**:
- T+0: Onboarding call en <24h hábiles
- Reporte trimestral ACA™
- Review de contrato al mes 3 (fin del compromiso mínimo)

### Capa 5 — Expansión / cross-sell

```
ARP compradora de curso $97–$497 ──► (6 meses) ──► invitación a Express $497 (upgrade academia → consultoría)
Express cerrada ──► (1 mes) ──► propuesta Professional $1.200
Professional cerrada ──► (2 meses) ──► propuesta Retención $1.500/mes
Cliente Retención ──► (3 meses) ──► testimonial + caso de estudio público
Maratón comprador ──► grabaciones Maratón + libro 15-nov + Pack RICFE
```

### Capa 6 — Firewall Sonja Kalos

- CSS distinto, dominio distinto, Stripe product metadata distinto (`marca: sonja-kalos`).
- Zero cross-link ni mención desde las otras 3 webs.
- ORCID NO se usa en Sonja Kalos.
- Marca personal "Sonia" NO aparece en Sonja Kalos.

## 3. Correcciones de diseño por marca

### blumdigitalpr.com (prioridad 🔴 urgente)
- Reescribir landing `/auditoria` con los 3 SKU, precios visibles, botones Stripe.
- Añadir sección testimonios (Amcham, SFIC, UIDE) — pedir citas reales a Sonia.
- Añadir FAQ con "qué recibes", "en cuánto tiempo", "cómo pagas".
- Unificar naming: eliminar "Diagnóstico ACA" conceptual, usar "Auditoría ACA™" en toda la web.
- Añadir chat SofIA con lead qualifier → MailerLite.
- Ver `marcas/blum-digital-pr/landing-auditoria-spec.md`.

### academiaderelacionespublicas.com (prioridad 🔴 libro 9 días)
- Añadir banner y landing `/libro` para preventa 15-nov.
- Añadir sección `/maraton-grabaciones` con payment link.
- Course cards: cambiar a botón directo a Stripe Payment Link.
- Testimonials: pedir 3 citas a compradores recientes (hay ~20 en últimos 30 días).
- Ver `marcas/academia-arp/landing-libro-15nov-spec.md`.

### soniayanez.com (prioridad 🟡 narrativa)
- Hero: cambiar "Investigadora en reputación algorítmica" → **"Investigadora independiente en reputación algorítmica, RRPP 6.0 e IA"**.
- Añadir "Afiliación: Alpen-Adria-Universität Klagenfurt (doctorando) · Academia ARP (fundadora)".
- Eliminar o minimizar cross-links comerciales desde el body principal — moverlos a un footer "Mis proyectos".
- Añadir Speaker Kit público accesible desde nav.
- Ver `marcas/sonia-yanez/correcciones-web.md`.

## 4. Decisiones estructurales

1. **Stripe = fuente única de verdad para precios**. La web nunca hardcodea un precio distinto al del Payment Link.
2. **Un Stripe Payment Link = un botón público**. Nunca un formulario que después lleva a un correo.
3. **MailerLite segmenta por `source` tag al capturar lead**. Nada va a un grupo genérico.
4. **Calendly = agenda compartida para sesiones post-compra**. Un solo calendario, varios event types (Express 60min / Professional 60min / Retención onboarding 60min).
5. **Firewall Sonja Kalos**: zero cruce con las otras 3 marcas, siempre.

## 5. Métricas que vigilar (dashboard mensual)

| Métrica | Meta Q1 2027 |
|---|---|
| MRR Retención Blum | $3.000 (2 clientes) |
| Express vendidas/mes | 4 ($1.988) |
| Professional vendidas/mes | 1 ($1.200) |
| Conversión landing Blum | ≥2% |
| Preventa libro (al 15-nov) | 100 copias |
| Grabaciones Maratón vendidas/mes | 10 |
| Nurture Blum open rate | ≥35% |
| Cross-sell ARP→Express | ≥1/mes |

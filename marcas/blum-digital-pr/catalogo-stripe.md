# Catálogo Stripe — Blum Digital PR

> Cuenta Stripe `acct_1Sh47w9D6PmzLXgN` (Sonia Yánez · Austria · USD · live mode).
> Creado 6-nov-2026 por Jefe de Despacho tras auditoría. Precios según CLAUDE.md.

## Productos activos

| Producto | Product ID | Price ID | Precio | Tipo | Payment Link |
|---|---|---|---|---|---|
| Auditoría ACA™ Express | `prod_VZrzQThhzSfxlF` | `price_1UYiFH9D6PmzLXgNRtiqomcS` | $497 USD | Una vez | https://buy.stripe.com/aFa7sF1yfa7scSjgvRc3m0g |
| Auditoría ACA™ Professional | `prod_VZs2PdyB88F9f6` | `price_1UYiIs9D6PmzLXgNtMTdNd4K` | $1.200 USD | Una vez | https://buy.stripe.com/aFa00d90HgvQ7xZ93pc3m0h |
| Retención Mensual Blum Digital PR | `prod_VZy7HRgoNzb1o9` | `price_1UYoB99D6PmzLXgNpbgkWXOg` | $1.500 USD / mes | Suscripción · mínimo 3 meses | https://buy.stripe.com/9B69ANa4LcfA4lNgvRc3m0i |

**Metadata por producto**: `marca: blum-digital-pr`, `tipo: {auditoria-express|auditoria-professional|retencion-mensual}`, `origen: ai_hq`.

## Promesa comprometida en el checkout

### Express ($497) — 5 días hábiles
1. Intake y propuesta de sesión de 60 min en las primeras 24 h hábiles.
2. Reporte ejecutivo con ACA-Score inicial + 5 acciones priorizadas al día 5.
3. Sesión de 60 min con Sonia.

### Professional ($1.200) — 15 días hábiles
1. Intake completo y calendario de 3 sesiones en las primeras 24 h hábiles.
2. Reporte ejecutivo con ACA-Score inicial + plan de intervención a 90 días al día 15.
3. 3 sesiones de 60 min con Sonia.

### Retención ($1.500/mes) — compromiso mínimo 3 meses
1. Onboarding y primera sesión mensual en las primeras 24 h hábiles.
2. Monitoreo de reputación algorítmica.
3. 4 entregables/mes.
4. Reporte ACA™ trimestral.
5. Cancelación libre a partir del 4º mes.

## Qué queda por hacer (dependencia operativa)

- [ ] Activar las 4 secuencias de MailerLite en draft:
  - `Blum - Bienvenida Lead Magnet Playbook ACA` (`182682168523228829`)
  - `Blum - Secuencia Campaña Diagnóstico ACA` (`182682207628822386`)
  - `Blum - Post-Compra Diagnóstico ACA` (`182682244296476415`)
  - `Post-Auditoría ACA™ — Seguimiento y Upsell` (`183216699591362245`)
- [ ] Serie `BLM-01` (4 correos T0/T+24h/T+1/T+7) sin disparador — necesita trigger de "suscriptor entra a grupo Compradores Express" para activarse.
- [ ] Añadir los 3 payment links al pie de los pitches comerciales en blumdigitalpr.com.
- [ ] Plantilla de intake Express (Google Form o Notion) enlazada desde el email T+0.
- [ ] Flujo de calendario: integrar Calendly a la confirmación de Express (sesión de 60 min).
- [ ] Decidir impuestos: los productos están con `tax_code: txcd_20030000` (consulting services). `automatic_tax: false` — revisar si aplica tratamiento Austria/UE antes de primera venta a cliente UE.

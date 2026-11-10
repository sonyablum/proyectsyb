# Campaña preventa libro · Secuencia de 5 emails

> 10-nov-2026 · Jefe de Despacho.
> Lanzamiento: 15-nov-2026 · Payment Link: https://buy.stripe.com/14AdR34Kr4N83hJ6Vhc3m0j
> **Nada se envía sin aprobación explícita de Sonia** (regla CLAUDE.md).

## Sender y audiencia

- **From**: `info@academiaderelacionespublicas.com` *(verificar que esté verificado en MailerLite; si no, cambiar al verificado)*
- **From name**: `Sonia Yánez Blum · Academia ARP`
- **Reply-to**: `info@academiaderelacionespublicas.com`
- **Audiencia consolidada** (dedupe MailerLite automático):

| Grupo | ID | Subs | Open rate |
|---|---|---|---|
| Maratón 2026 · Registros post-evento | 199875771194410271 | 1.056 | 25,76% |
| Maratón 2026 · Free | 194655163413169474 | 378 | 51,88% |
| Lista personal · Grupo ARP | 186663392917849450 | 176 | 51,80% |
| Maratón PRO 2026 · no completaron pago | 199866722089436750 | 34 | 46,10% |
| VIP MARATON | 166432198967166787 | 18 | 60,68% |
| Maratón 2026 · Reporte completo | 200138603328701732 | 16 | 78,33% |
| Maratón PRO 2026 · compradores | 195962306525398237 | 12 | 75,95% |
| Compradores Manual RICFE V3 | 184620027029227361 | 10 | 72,97% |
| Compradores Sistema RICFE ($47) | 184666969447859748 | 4 | 91,51% |

Total nominal: ~1.704 · estimación tras dedupe: ~1.400.

## Calendario

| # | Fecha envío | Zona Austria | Asunto | Objetivo |
|---|---|---|---|---|
| E1 | mié 11-nov | 10:00 | ¿Qué dice la IA de ti? El libro sale el 15-nov · preventa $19 | Anuncio preventa |
| E2 | vie 13-nov | 10:00 | Preview capítulo 2: cómo nos leen los LLMs | Prueba de valor |
| E3 | sáb 14-nov | 18:00 | Mañana sube a $29 · últimas horas de preventa | Urgencia |
| E4 | dom 15-nov | 09:00 | Tu libro está en tu correo · gracias | Entrega del PDF |
| E5 | lun 17-nov | 10:00 | Precio regular activo · última llamada a $29 | Cierre para los no compradores |

---

## E1 · 11-nov · Anuncio preventa

**Asunto**: ¿Qué dice la IA de ti? El libro sale el 15-nov · preventa $19

**HTML**:

```html
<!DOCTYPE html>
<html lang="es"><head><meta charset="UTF-8"></head>
<body style="margin:0;padding:0;background:#FAF8F3;font-family:-apple-system,BlinkMacSystemFont,sans-serif;color:#2B2438;line-height:1.55;">
<table role="presentation" style="width:100%;border-collapse:collapse;" cellspacing="0" cellpadding="0" border="0">
<tr><td align="center" style="padding:32px 16px;">
<table role="presentation" style="max-width:580px;width:100%;background:#fff;border-radius:8px;" cellspacing="0" cellpadding="0" border="0">
<tr><td style="padding:40px 24px 24px;text-align:center;">
<img src="https://raw.githubusercontent.com/sonyablum/proyectsyb/claude/fix-failing-projects-zu2U4/marcas/academia-arp/assets/portada-libro.webp" alt="Reputación algorítmica y GEO para Relaciones Públicas" width="180" style="max-width:180px;height:auto;border-radius:6px;box-shadow:0 10px 24px rgba(107,76,143,.3);display:block;margin:0 auto;">
</td></tr>
<tr><td style="padding:0 32px;">
<p style="font-size:12px;color:#6B4C8F;letter-spacing:2px;text-transform:uppercase;margin:0 0 12px;font-weight:700;">Lanzamiento · 15 de noviembre de 2026</p>
<h1 style="font-size:28px;line-height:1.2;color:#2B2438;margin:0 0 20px;font-weight:700;">¿Qué dice hoy la IA de ti?</h1>
<p style="font-size:16px;color:#4A4255;margin:0 0 16px;">La IA generativa ya está respondiendo preguntas sobre tu marca, tu organización o sobre ti como profesional. Y lo hace antes de que puedas intervenir.</p>
<p style="font-size:16px;color:#4A4255;margin:0 0 16px;">Durante años trabajamos auditando cómo describen las marcas en los medios. Hoy el espejo es otro: ChatGPT, Claude, Gemini, Perplexity. Y responde con una síntesis que define autoridad percibida.</p>
<p style="font-size:16px;color:#4A4255;margin:0 0 16px;">El nuevo libro reúne el marco con el que trabajo:</p>
<p style="font-size:18px;color:#6B4C8F;font-weight:700;margin:0 0 6px;">Reputación algorítmica y GEO para Relaciones Públicas</p>
<p style="font-size:15px;color:#4A4255;font-style:italic;margin:0 0 20px;">Cómo lograr que la IA reconozca, describa y cite a tu marca, tu organización y tus líderes.</p>
<p style="font-size:16px;color:#4A4255;margin:0 0 16px;">Dentro: el Marco ACA™, el ACA-Score™, GEO aplicado a RRPP, AI Governance y 20 prompts del método RICFE®.</p>
<table role="presentation" style="width:100%;margin:28px 0;background:#F3EDE2;border-radius:6px;" cellspacing="0" cellpadding="0" border="0"><tr><td style="padding:20px 24px;">
<p style="margin:0;font-size:14px;color:#4A4255;">Preventa hasta el <strong>15-nov</strong>:</p>
<p style="margin:4px 0 0;font-size:28px;color:#6B4C8F;font-weight:700;"><span style="color:#8A7E9B;font-size:18px;text-decoration:line-through;">$29</span> &nbsp;$19 USD</p>
<p style="margin:8px 0 0;font-size:13px;color:#8A7E9B;">Lo recibes en PDF, en tu correo, el mismo día del lanzamiento.</p>
</td></tr></table>
</td></tr>
<tr><td align="center" style="padding:16px 24px 24px;">
<a href="https://buy.stripe.com/14AdR34Kr4N83hJ6Vhc3m0j" style="display:inline-block;background:#E85D3C;color:#fff;text-decoration:none;padding:18px 44px;border-radius:6px;font-weight:700;font-size:17px;">Reservar mi copia — $19</a>
</td></tr>
<tr><td style="padding:16px 32px 32px;font-size:14px;color:#6B5E7A;">
<p style="margin:0 0 6px;">Un abrazo,</p>
<p style="margin:0 0 4px;font-weight:600;">Sonia Yánez Blum</p>
<p style="margin:0;color:#8A7E9B;font-size:13px;">Investigadora independiente en reputación algorítmica y opinión pública · Creadora del Marco ACA™</p>
</td></tr>
<tr><td style="padding:24px 32px;font-size:12px;color:#8A7E9B;text-align:center;border-top:1px solid #E5DECE;">
<p style="margin:0 0 6px;">Academia de Relaciones Públicas ARP</p>
<p style="margin:0;">¿Ya no quieres recibir estos correos? <a href="{$unsubscribe}" style="color:#6B4C8F;">Darse de baja</a></p>
</td></tr>
</table>
</td></tr>
</table>
</body></html>
```

---

## E2 · 13-nov · Preview capítulo

**Asunto**: Preview capítulo 2: cómo nos leen los LLMs

**Resumen del contenido**: entrega 3 párrafos del capítulo 2 como preview gratis para activar deseo. Soft CTA al final.

**HTML**:

```html
<!DOCTYPE html>
<html lang="es"><head><meta charset="UTF-8"></head>
<body style="margin:0;padding:0;background:#FAF8F3;font-family:-apple-system,BlinkMacSystemFont,sans-serif;color:#2B2438;line-height:1.6;">
<table role="presentation" style="width:100%;border-collapse:collapse;" cellspacing="0" cellpadding="0" border="0">
<tr><td align="center" style="padding:32px 16px;">
<table role="presentation" style="max-width:580px;width:100%;background:#fff;border-radius:8px;" cellspacing="0" cellpadding="0" border="0">
<tr><td style="padding:32px 32px 8px;">
<p style="font-size:12px;color:#6B4C8F;letter-spacing:2px;text-transform:uppercase;margin:0 0 12px;font-weight:700;">Preview · Capítulo 2</p>
<h1 style="font-size:26px;line-height:1.2;color:#2B2438;margin:0 0 24px;font-weight:700;">Cómo nos leen los LLMs.</h1>
<p style="font-size:16px;color:#4A4255;margin:0 0 16px;font-style:italic;">(Un extracto del libro que sale el domingo.)</p>
<div style="border-left:4px solid #6B4C8F;padding:4px 0 4px 20px;margin:24px 0;color:#4A4255;">
<p style="font-size:16px;margin:0 0 14px;">"Cuando un usuario pregunta por una persona o una marca, un modelo de lenguaje no 'recuerda' esa entidad: la reconstruye. Toma fragmentos de su corpus de entrenamiento, los pesa por frecuencia y autoridad percibida, y produce una síntesis que se presenta como respuesta neutral.</p>
<p style="font-size:16px;margin:0 0 14px;">Esa síntesis no refleja el mejor contenido disponible sobre la entidad. Refleja el contenido más citado, más coherente y más amplificado. Por eso una empresa con una web premiada pero poca presencia editorial puede quedar ausente en la respuesta, y una autora con pocos artículos pero muy citados puede dominarla.</p>
<p style="font-size:16px;margin:0;">La reputación algorítmica es, por tanto, un fenómeno distinto al posicionamiento SEO o al share of voice en medios. Es la huella sintetizada que la IA produce al preguntarle por ti."</p>
</div>
<p style="font-size:14px;color:#8A7E9B;font-style:italic;margin:16px 0 24px;">— Reputación algorítmica y GEO para Relaciones Públicas, capítulo 2</p>
<p style="font-size:16px;color:#4A4255;margin:0 0 16px;">Si quieres los otros 7 capítulos, los 3 casos de estudio y los 20 prompts del método RICFE®, hay <strong>48 horas</strong> para reservar a precio preventa.</p>
<table role="presentation" style="width:100%;margin:24px 0;background:#F3EDE2;border-radius:6px;" cellspacing="0" cellpadding="0" border="0"><tr><td style="padding:16px 24px;">
<p style="margin:0;font-size:14px;color:#4A4255;">Preventa (hasta domingo 15-nov):</p>
<p style="margin:4px 0 0;font-size:24px;color:#6B4C8F;font-weight:700;"><span style="color:#8A7E9B;font-size:16px;text-decoration:line-through;">$29</span> &nbsp;$19 USD</p>
</td></tr></table>
</td></tr>
<tr><td align="center" style="padding:8px 24px 24px;">
<a href="https://buy.stripe.com/14AdR34Kr4N83hJ6Vhc3m0j" style="display:inline-block;background:#E85D3C;color:#fff;text-decoration:none;padding:16px 36px;border-radius:6px;font-weight:700;font-size:16px;">Reservar por $19</a>
</td></tr>
<tr><td style="padding:16px 32px 32px;font-size:14px;color:#6B5E7A;">
<p style="margin:0 0 4px;">Sonia Yánez Blum</p>
<p style="margin:0;color:#8A7E9B;font-size:13px;">Creadora del Marco ACA™</p>
</td></tr>
<tr><td style="padding:24px 32px;font-size:12px;color:#8A7E9B;text-align:center;border-top:1px solid #E5DECE;">
<p style="margin:0 0 6px;">Academia de Relaciones Públicas ARP</p>
<p style="margin:0;"><a href="{$unsubscribe}" style="color:#6B4C8F;">Darse de baja</a></p>
</td></tr>
</table>
</td></tr>
</table>
</body></html>
```

---

## E3 · 14-nov tarde · Urgencia

**Asunto**: Mañana sube a $29 · últimas horas de preventa

**HTML**:

```html
<!DOCTYPE html>
<html lang="es"><head><meta charset="UTF-8"></head>
<body style="margin:0;padding:0;background:#FAF8F3;font-family:-apple-system,BlinkMacSystemFont,sans-serif;color:#2B2438;line-height:1.55;">
<table role="presentation" style="width:100%;border-collapse:collapse;" cellspacing="0" cellpadding="0" border="0">
<tr><td align="center" style="padding:32px 16px;">
<table role="presentation" style="max-width:580px;width:100%;background:#fff;border-radius:8px;" cellspacing="0" cellpadding="0" border="0">
<tr><td style="background:#6B4C8F;color:#FAF8F3;padding:12px 24px;text-align:center;font-size:13px;letter-spacing:1px;font-weight:600;border-radius:8px 8px 0 0;">
⏳ ÚLTIMAS HORAS · MAÑANA SUBE A $29
</td></tr>
<tr><td style="padding:40px 32px 16px;text-align:center;">
<img src="https://raw.githubusercontent.com/sonyablum/proyectsyb/claude/fix-failing-projects-zu2U4/marcas/academia-arp/assets/portada-libro.webp" alt="Portada del libro" width="140" style="max-width:140px;height:auto;border-radius:6px;box-shadow:0 10px 24px rgba(107,76,143,.3);display:block;margin:0 auto;">
</td></tr>
<tr><td style="padding:0 32px;">
<h1 style="font-size:26px;line-height:1.2;color:#2B2438;margin:0 0 20px;font-weight:700;text-align:center;">Mañana sale el libro.</h1>
<p style="font-size:16px;color:#4A4255;margin:0 0 16px;text-align:center;">Y mañana el precio sube a $29.</p>
<p style="font-size:16px;color:#4A4255;margin:0 0 16px;">Si todavía estabas pensándolo: este es el momento. El valor es el mismo mañana que hoy. La diferencia son $10 que ya no ahorras.</p>
<table role="presentation" style="width:100%;margin:24px 0;background:#F3EDE2;border-radius:6px;" cellspacing="0" cellpadding="0" border="0"><tr><td style="padding:16px 24px;text-align:center;">
<p style="margin:0;font-size:13px;color:#8A7E9B;text-transform:uppercase;letter-spacing:1px;">Hoy</p>
<p style="margin:4px 0 0;font-size:32px;color:#6B4C8F;font-weight:700;">$19 USD</p>
<p style="margin:4px 0 0;font-size:13px;color:#8A7E9B;">Mañana: $29</p>
</td></tr></table>
</td></tr>
<tr><td align="center" style="padding:16px 24px 24px;">
<a href="https://buy.stripe.com/14AdR34Kr4N83hJ6Vhc3m0j" style="display:inline-block;background:#E85D3C;color:#fff;text-decoration:none;padding:18px 44px;border-radius:6px;font-weight:700;font-size:17px;">Reservar ahora — $19</a>
</td></tr>
<tr><td style="padding:16px 32px 32px;font-size:14px;color:#6B5E7A;text-align:center;">
<p style="margin:0;">Nos vemos mañana en tu correo con el PDF.</p>
<p style="margin:12px 0 0;font-weight:600;">Sonia</p>
</td></tr>
<tr><td style="padding:24px 32px;font-size:12px;color:#8A7E9B;text-align:center;border-top:1px solid #E5DECE;">
<p style="margin:0 0 6px;">Academia de Relaciones Públicas ARP</p>
<p style="margin:0;"><a href="{$unsubscribe}" style="color:#6B4C8F;">Darse de baja</a></p>
</td></tr>
</table>
</td></tr>
</table>
</body></html>
```

---

## E4 · 15-nov mañana · Entrega

**Asunto**: Tu libro está en tu correo · gracias

> ⚠️ Este email se envía **solo a compradores** (grupo que se auto-crea cuando llega el pago en Stripe → MailerLite via webhook o manual). NO a la audiencia general.

**HTML**:

```html
<!DOCTYPE html>
<html lang="es"><head><meta charset="UTF-8"></head>
<body style="margin:0;padding:0;background:#FAF8F3;font-family:-apple-system,BlinkMacSystemFont,sans-serif;color:#2B2438;line-height:1.55;">
<table role="presentation" style="width:100%;border-collapse:collapse;" cellspacing="0" cellpadding="0" border="0">
<tr><td align="center" style="padding:32px 16px;">
<table role="presentation" style="max-width:580px;width:100%;background:#fff;border-radius:8px;" cellspacing="0" cellpadding="0" border="0">
<tr><td style="padding:40px 32px 16px;text-align:center;">
<img src="https://raw.githubusercontent.com/sonyablum/proyectsyb/claude/fix-failing-projects-zu2U4/marcas/academia-arp/assets/portada-libro.webp" alt="Portada" width="180" style="max-width:180px;height:auto;border-radius:6px;box-shadow:0 10px 24px rgba(107,76,143,.3);display:block;margin:0 auto;">
</td></tr>
<tr><td style="padding:0 32px;">
<h1 style="font-size:28px;line-height:1.2;color:#2B2438;margin:0 0 20px;font-weight:700;">Aquí está tu libro.</h1>
<p style="font-size:16px;color:#4A4255;margin:0 0 16px;">Gracias por haber confiado en la preventa. Significa mucho que lo recibas hoy, el día del lanzamiento.</p>
<p style="font-size:16px;color:#4A4255;margin:0 0 20px;">Tu PDF está adjunto a este correo. Si no lo ves, está también disponible aquí:</p>
</td></tr>
<tr><td align="center" style="padding:8px 24px 24px;">
<a href="LINK_PDF_DRIVE_O_DOWNLOAD" style="display:inline-block;background:#6B4C8F;color:#fff;text-decoration:none;padding:16px 40px;border-radius:6px;font-weight:700;font-size:17px;">📘 Descargar el libro</a>
</td></tr>
<tr><td style="padding:16px 32px;">
<p style="font-size:16px;color:#4A4255;margin:0 0 16px;">Algunas cosas que te sugiero mientras lo lees:</p>
<ol style="font-size:16px;color:#4A4255;padding-left:20px;margin:0 0 24px;">
<li style="margin-bottom:8px;">Léelo con los 4 LLMs abiertos en otra pestaña. Vale más aplicar un capítulo que leer tres.</li>
<li style="margin-bottom:8px;">Los 20 prompts del apéndice están listos para copiar y pegar.</li>
<li style="margin-bottom:8px;">Si algún concepto no está claro, respóndeme a este correo. Las dudas que recibo esta semana entran en el próximo workshop.</li>
</ol>
<div style="background:#F3EDE2;border-radius:6px;padding:20px 24px;margin:24px 0;">
<p style="margin:0 0 10px;font-size:15px;color:#4A4255;"><strong>¿Lo quieres aplicar a tu marca o a un cliente?</strong></p>
<p style="margin:0;font-size:14px;color:#6B5E7A;">Blum Digital PR tiene una auditoría ACA™ Express de 5 días hábiles ($497). Reporte + sesión con cada compra. <a href="https://blumdigitalpr.com/auditoria" style="color:#6B4C8F;">Ver aquí</a>.</p>
</div>
</td></tr>
<tr><td style="padding:16px 32px 32px;font-size:14px;color:#6B5E7A;">
<p style="margin:0 0 6px;">Gracias de corazón,</p>
<p style="margin:0 0 4px;font-weight:600;">Sonia Yánez Blum</p>
<p style="margin:0;color:#8A7E9B;font-size:13px;">Creadora del Marco ACA™</p>
</td></tr>
<tr><td style="padding:24px 32px;font-size:12px;color:#8A7E9B;text-align:center;border-top:1px solid #E5DECE;">
<p style="margin:0 0 6px;">Academia de Relaciones Públicas ARP</p>
<p style="margin:0;"><a href="{$unsubscribe}" style="color:#6B4C8F;">Darse de baja</a></p>
</td></tr>
</table>
</td></tr>
</table>
</body></html>
```

**Nota técnica E4**: el PDF se puede entregar de 3 formas:
1. **Adjunto** en el email (MailerLite lo permite hasta ~5 MB).
2. **Link a Drive** público con descarga directa.
3. **Trigger automation** cuando llegue el pago Stripe (en vez de campaña masiva). Recomendado para los que compren en los 7 días tras el 15-nov.

Sonia debe decidir y pasar el link del PDF subido a Drive.

---

## E5 · 17-nov · Última llamada precio regular

**Asunto**: Precio regular activo · última llamada a $29

> Solo a **no compradores** (excluir grupo de compradores del libro).

**HTML**:

```html
<!DOCTYPE html>
<html lang="es"><head><meta charset="UTF-8"></head>
<body style="margin:0;padding:0;background:#FAF8F3;font-family:-apple-system,BlinkMacSystemFont,sans-serif;color:#2B2438;line-height:1.55;">
<table role="presentation" style="width:100%;border-collapse:collapse;" cellspacing="0" cellpadding="0" border="0">
<tr><td align="center" style="padding:32px 16px;">
<table role="presentation" style="max-width:580px;width:100%;background:#fff;border-radius:8px;" cellspacing="0" cellpadding="0" border="0">
<tr><td style="padding:40px 32px 24px;">
<h1 style="font-size:26px;line-height:1.3;color:#2B2438;margin:0 0 20px;font-weight:700;">El libro salió el domingo.</h1>
<p style="font-size:16px;color:#4A4255;margin:0 0 16px;">Si por cualquier razón no llegaste a la preventa, quería contarte dos cosas:</p>
<p style="font-size:16px;color:#4A4255;margin:0 0 16px;"><strong>1.</strong> El libro está disponible desde ayer al precio regular de $29. Lo recibes en tu correo al instante tras el pago.</p>
<p style="font-size:16px;color:#4A4255;margin:0 0 16px;"><strong>2.</strong> Este es el último correo que te mando sobre el libro. Si no te interesa, perfecto, lo cierro aquí.</p>
<p style="font-size:16px;color:#4A4255;margin:0 0 16px;">Si sí te interesa:</p>
<table role="presentation" style="width:100%;margin:24px 0;background:#F3EDE2;border-radius:6px;" cellspacing="0" cellpadding="0" border="0"><tr><td style="padding:16px 24px;text-align:center;">
<p style="margin:0;font-size:13px;color:#8A7E9B;text-transform:uppercase;letter-spacing:1px;">Precio regular</p>
<p style="margin:4px 0 0;font-size:32px;color:#6B4C8F;font-weight:700;">$29 USD</p>
<p style="margin:4px 0 0;font-size:13px;color:#8A7E9B;">Entrega inmediata del PDF</p>
</td></tr></table>
</td></tr>
<tr><td align="center" style="padding:8px 24px 24px;">
<a href="https://buy.stripe.com/14AdR34Kr4N83hJ6Vhc3m0j" style="display:inline-block;background:#E85D3C;color:#fff;text-decoration:none;padding:18px 44px;border-radius:6px;font-weight:700;font-size:17px;">Comprar el libro — $29</a>
</td></tr>
<tr><td style="padding:16px 32px 32px;font-size:14px;color:#6B5E7A;">
<p style="margin:0 0 6px;">Un abrazo,</p>
<p style="margin:0 0 4px;font-weight:600;">Sonia</p>
</td></tr>
<tr><td style="padding:24px 32px;font-size:12px;color:#8A7E9B;text-align:center;border-top:1px solid #E5DECE;">
<p style="margin:0 0 6px;">Academia de Relaciones Públicas ARP</p>
<p style="margin:0;"><a href="{$unsubscribe}" style="color:#6B4C8F;">Darse de baja</a></p>
</td></tr>
</table>
</td></tr>
</table>
</body></html>
```

**Importante**: antes del 17-nov, cambiar el Payment Link a precio $29 (crear nuevo precio en Stripe para `prod_VTKRkYLzSXl0Gn` por $29 regular + nuevo Payment Link, o actualizar el default_price). El link de este email debe apuntar al regular, no al de preventa.

---

## Qué falta de Sonia

1. **Verificar sender** `info@academiaderelacionespublicas.com` en MailerLite. Si usa otro, me dice y actualizamos.
2. **PDF del libro** subido a Drive (para E4 — o decidir si va adjunto por MailerLite).
3. **Autorización de envío** por cada campaña (CLAUDE.md: Sonia envía).
4. Si hay feedback del tono, copy o grupos, lo ajusto en el draft.

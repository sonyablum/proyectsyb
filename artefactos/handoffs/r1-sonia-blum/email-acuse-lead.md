# 📧 Email automatizado de acuse al lead — R1

> Este email lo envía MailerLite **automáticamente** cuando el lead entra al grupo `blum-leads-r1`. NO requiere acción manual.
> Importar como automation en MailerLite usando el HTML de abajo.

## Configuración MailerLite

- **Trigger**: `Subscriber joins group → blum-leads-r1`
- **Delay**: `Inmediato`
- **From name**: `Sonia Yánez Blum · Blum Digital PR`
- **From email**: `hola@blumdigitalpr.com` *(o el dominio oficial · CONFIRMAR)*
- **Reply-to**: `hola@blumdigitalpr.com`

## Asunto

```
Recibí tu mensaje, {{name}} — te respondo en menos de {{custom.sla_horas}}h
```

## Cuerpo (HTML/texto)

```html
<p>Hola {{name}},</p>

<p>Soy Sonia. Recibí tu mensaje sobre <strong>{{custom.company|default:"tu proyecto"}}</strong> y quiero confirmarte que lo tengo en mi radar.</p>

<p>En las próximas <strong>{{custom.sla_horas}} horas hábiles</strong> alguien de mi equipo en Blum Digital PR se pondrá en contacto contigo para una conversación corta de diagnóstico (20 min, sin compromiso). Allí veremos si una <strong>Auditoría de Reputación Algorítmica</strong> es lo que tu organización necesita ahora mismo.</p>

<p>Mientras tanto, si te sirve de contexto, puedes leer mi último preprint sobre el tema: <a href="https://doi.org/10.5281/zenodo.18802347">Teoría de la Autoridad Algorítmica</a> (DOI Zenodo, abierto).</p>

<p>Cualquier urgencia, este mismo email funciona como canal directo.</p>

<p>Un abrazo desde Klagenfurt,</p>

<p><strong>Sonia Yánez Blum</strong><br>
Investigadora independiente en Reputación Algorítmica · Fundadora de Blum Digital PR<br>
ORCID: 0000-0002-6695-8129</p>

<hr style="border:none;border-top:1px solid #eee;margin:24px 0;">

<p style="font-size:11px;color:#777;">
Recibiste este email porque escribiste a Sonia o a Blum Digital PR. 
Si no fuiste tú, ignora este mensaje — no te volveremos a escribir. 
Si quieres dejar de recibir, <a href="{{unsubscribe}}">date de baja aquí</a>.
</p>
```

## Versión texto plano (fallback)

```
Hola {{name}},

Soy Sonia. Recibí tu mensaje sobre {{custom.company}} y quiero confirmarte que 
lo tengo en mi radar.

En las próximas {{custom.sla_horas}} horas hábiles, alguien de mi equipo en 
Blum Digital PR se pondrá en contacto contigo para una conversación corta de 
diagnóstico (20 min, sin compromiso). Allí veremos si una Auditoría de 
Reputación Algorítmica es lo que tu organización necesita ahora mismo.

Mientras tanto, si te sirve de contexto, puedes leer mi último preprint:
https://doi.org/10.5281/zenodo.18802347

Un abrazo desde Klagenfurt,

Sonia Yánez Blum
Investigadora independiente en Reputación Algorítmica
Fundadora de Blum Digital PR
ORCID: 0000-0002-6695-8129
```

## Reglas de este email (no romper)

1. ✅ Firma comercial completa: "consultora · fundadora de Blum Digital PR".
2. ✅ Cita 1 DOI público (TAA) para autoridad — el lead es comercial, así que se cita al DOI desde el marco comercial sin caer en CTA de venta. Si se cita más, ya pasa a marketing académico (académico ≠ comercial).
3. ❌ NUNCA dice "doctoranda" ni "candidata doctoral".
4. ❌ NUNCA menciona FACE™, Protocolo GEAC, ACA Seal™, ACA-Score™ v3 (no públicos).
5. ❌ NUNCA menciona Sonja Kalos.
6. ✅ Idioma: español neutro.
7. ✅ Compromiso de SLA explícito (refuerza profesionalidad).
8. ✅ Unsubscribe visible (GDPR-compliant).

## Variantes A/B (para optimizar después)

- **A** (esta): tono cercano + DOI académico para autoridad.
- **B**: tono más corporativo + mención de retención $1,500/mes para anclar pricing.

Probar después del primer mes con datos reales.

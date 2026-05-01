# 📧 Email de notificación interna — R1

> Este email lo envía Make **automáticamente** al owner Blum N1 (con CC a la CEO) en cuanto entra un lead R1. NO requiere acción manual.

## Configuración Make (módulo `email:Send`)

- **From**: `automatizacion@blumdigitalpr.com` o SMTP corporativo
- **To**: `{{owner_n1_email}}` (variable seteada en módulo 2 del blueprint)
- **CC**: `soniayanezblum@gmail.com` (CEO)
- **Reply-to**: `{{owner_n1_email}}`

## Asunto

```
[R1 · {{urgencia | upper}}] Nuevo lead Blum: {{empresa}} — {{lead_nombre}} (SLA {{sla_horas}}h)
```

Ejemplo real:
```
[R1 · CALIENTE] Nuevo lead Blum: Acme SA — Juan Pérez (SLA 4h)
```

## Cuerpo

```html
<p><strong>Nuevo lead recibido vía R1 (Sonia → Blum)</strong></p>

<table style="border-collapse:collapse;font-family:Arial,sans-serif;font-size:14px;">
<tr><td style="padding:6px 12px;border:1px solid #ddd;background:#f7f7f7;"><strong>Handoff ID</strong></td>
    <td style="padding:6px 12px;border:1px solid #ddd;font-family:monospace;">{{handoff_id}}</td></tr>
<tr><td style="padding:6px 12px;border:1px solid #ddd;background:#f7f7f7;"><strong>Lead</strong></td>
    <td style="padding:6px 12px;border:1px solid #ddd;">{{lead_nombre}} &lt;{{lead_email}}&gt;</td></tr>
<tr><td style="padding:6px 12px;border:1px solid #ddd;background:#f7f7f7;"><strong>Empresa</strong></td>
    <td style="padding:6px 12px;border:1px solid #ddd;">{{empresa}} ({{pais}})</td></tr>
<tr><td style="padding:6px 12px;border:1px solid #ddd;background:#f7f7f7;"><strong>Canal origen</strong></td>
    <td style="padding:6px 12px;border:1px solid #ddd;">{{canal_origen}}</td></tr>
<tr><td style="padding:6px 12px;border:1px solid #ddd;background:#f7f7f7;"><strong>Mensaje (resumen IA)</strong></td>
    <td style="padding:6px 12px;border:1px solid #ddd;">{{mensaje_resumen}}</td></tr>
<tr><td style="padding:6px 12px;border:1px solid #ddd;background:#f7f7f7;"><strong>Score IA</strong></td>
    <td style="padding:6px 12px;border:1px solid #ddd;">{{score_ia}} / 5</td></tr>
<tr><td style="padding:6px 12px;border:1px solid #ddd;background:#f7f7f7;"><strong>Recomendación IA</strong></td>
    <td style="padding:6px 12px;border:1px solid #ddd;">{{recomendacion_ia}}</td></tr>
<tr><td style="padding:6px 12px;border:1px solid #ddd;background:#f7f7f7;"><strong>Urgencia</strong></td>
    <td style="padding:6px 12px;border:1px solid #ddd;color:{{if(urgencia='caliente';'#c00';'#666')}};"><strong>{{urgencia | upper}}</strong></td></tr>
<tr><td style="padding:6px 12px;border:1px solid #ddd;background:#fff3cd;"><strong>SLA N1</strong></td>
    <td style="padding:6px 12px;border:1px solid #ddd;background:#fff3cd;"><strong>{{sla_horas}} horas</strong> · vence {{deadline_n1}}</td></tr>
</table>

<h3>Tu acción ahora</h3>
<ol>
  <li>Lee el mensaje completo del lead en Notion: <a href="{{notion_url}}">abrir CRM</a></li>
  <li>Si la recomendación IA es <strong>Express</strong> y el lead matchea perfil → contesta con propuesta directa (plantilla en <code>artefactos/handoffs/r1-sonia-blum/</code>).</li>
  <li>Si es <strong>Professional</strong> o <strong>Retención</strong> → agenda diagnóstica de 20 min y avisa a la CEO.</li>
  <li>Marca el estado en Notion: <code>En curso</code> en cuanto contactes al lead.</li>
  <li>Si el lead tiene <strong>red flags</strong> (en notas IA) → revisa con la CEO antes de contactar.</li>
</ol>

<p><strong>Si no actúas en {{sla_horas}}h:</strong> el sistema escala automáticamente al Pdte. Blum (N2). Si N2 vence, escala a la CEO.</p>

<hr>

<p style="font-size:11px;color:#777;">
Sistema A2A · Ruta R1 · Sonia → Blum<br>
Handoff registrado en Drive: <code>AI-HQ/Pipeline/Handoffs/R1-Sonia-Blum/{{YYYY-MM}}/{{handoff_id}}.json</code>
</p>
```

## Versión texto plano (fallback)

```
NUEVO LEAD R1 (Sonia → Blum)

Handoff ID: {{handoff_id}}
Lead: {{lead_nombre}} <{{lead_email}}>
Empresa: {{empresa}} ({{pais}})
Canal: {{canal_origen}}

Mensaje (resumen IA):
{{mensaje_resumen}}

Score IA: {{score_ia}}/5
Recomendación IA: {{recomendacion_ia}}
Urgencia: {{urgencia | upper}}

SLA N1: {{sla_horas}}h — vence {{deadline_n1}}

ACCIÓN AHORA:
1. Abre Notion y lee el lead completo: {{notion_url}}
2. Contacta al lead en menos de {{sla_horas}}h
3. Marca estado "En curso" en Notion al contactar
4. Si red flags en notas IA, revisa con CEO antes

Si vence el SLA N1 → escala automático a Pdte. Blum (N2).
```

## Reglas

1. ✅ El owner N1 recibe TODO lo que necesita en el email — no debería abrir 5 herramientas para entender el lead.
2. ✅ CEO en CC para visibilidad total, no para acción.
3. ❌ NO incluir credenciales, tokens, ni IDs internos sensibles.
4. ❌ NO compartir el contenido de este email con terceros (es operativa interna).
5. ✅ Plantilla revisable cada trimestre para optimizar.

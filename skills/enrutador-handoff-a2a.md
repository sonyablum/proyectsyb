# 🔀 Skill — Enrutador de handoffs A2A

> Cómo identifica y enruta un mensaje entrante a una de las 6 rutas A2A del holding (o a "no es A2A").

## Inputs

- Texto del mensaje / email / formulario / WhatsApp / interacción.
- Canal de origen.
- Identidad del remitente (si es conocida).

## Output

JSON estructurado:

```json
{
  "es_handoff": true,
  "ruta_recomendada": "R1",
  "origen_marca": "Sonia Yanez",
  "destino_marca": "Blum Digital PR",
  "tipo": "Comercial - lead consultoria",
  "urgencia": "caliente",
  "score_clasificacion_ia": 4,
  "razonamiento": "1 línea con por qué",
  "red_flags": []
}
```

## Decisión por intención

### Detecta R1 (Sonia → Blum)
- Lead llega vía: web Sonia · podcast · LinkedIn Sonia · prensa · referido académico.
- Pide: consultoría · auditoría · implementación de IA · formación in-company.
- Mensaje suele citar: Marco ACA™ · Reputación Algorítmica · ACA-Score™ · DOIs.

### Detecta R2 (Sonia → ARP)
- Lead llega vía: web Sonia · podcast · LinkedIn Sonia.
- Pide: cursos · plantillas · curso a su equipo · acceso a la academia.
- Suele ser perfil B2C profesional individual.

### Detecta R3 (Blum → Sonia)
- Origen: equipo Blum (interno, no externo).
- Contenido: caso de éxito completado, listo para anonimizar y publicar.

### Detecta R4 (Blum → ARP)
- Origen: equipo Blum.
- Contenido: cliente Blum cuyo equipo necesita formación masiva (no consultoría 1-a-1).

### Detecta R5 (ARP → Sonia)
- Origen: plataforma ARP / instructor.
- Contenido: insight pedagógico interesante para investigación / podcast / columna.

### Detecta R6 (ARP → Blum)
- Origen: plataforma ARP.
- Contenido: alumno corporativo o senior que pide consultoría 1-a-1 (caso de upsell).

### Detecta "no es A2A"
- Spam · ofertas a Sonia · prensa pidiendo entrevista · Hase / académicos (van directo a Pdte. Sonia, no son handoff).

## Caliente vs tibio (para R1, R2, R6)

| Caliente | Tibio |
|---|---|
| Urgencia explícita ("necesitamos esto antes de X") | Exploración general |
| Empresa identificada con datos básicos | Email genérico sin contexto |
| Presupuesto mencionado | "¿cuánto cuesta?" sin más |
| Decisor en el contacto | Junior pidiendo info para alguien |
| Deadline claro | Sin fecha |

Score 4-5 → caliente. Score 1-3 → tibio. Score 0 → descalificar.

## Red flags (motivos de revisión humana)

- 🚩 Pide cosa fuera de catálogo (ej: bot de spam, "cripto-coach", lavado de imagen política).
- 🚩 Lenguaje agresivo o sospechoso.
- 🚩 Solicita datos sensibles antes de contratar.
- 🚩 Promete colaboración a cambio de "exposure".
- 🚩 Pide que Sonia firme algo no académico.
- 🚩 Menciona Sonja Kalos en contexto Blum/Sonia (firewall violation potential).
- 🚩 Pide acceso a Marco ACA™ no público (FACE WP, GEAC, Seal).

Si ≥ 1 red flag → **NO** ejecutar handoff automático. Marcar `es_handoff=false` y derivar a CEO.

## Reglas anti-canibalización del enrutador

1. ❌ Si destino_marca = `Sonja Kalos` y origen_marca ∈ {Sonia, Blum, ARP} → **bloqueo automático** + alerta crítica.
2. ❌ Si origen_marca = `Sonja Kalos` y destino_marca ∈ {Sonia, Blum, ARP} → **bloqueo automático** + alerta crítica.
3. ❌ Si el mensaje pide formación en metodología core (ACA-Score™, FACE™, GEAC, Seal, Reputación Algorítmica) y la marca destino es ARP → reenrutar a R1 o R4 (Blum) y registrar el intento.
4. ❌ Si el mensaje mezcla CTA comercial con cita de DOI Zenodo (académico ≠ comercial) → marcar para revisión humana.

## Implementación técnica

- Modelo: `gpt-4o-mini` (suficiente y barato).
- Prompt del sistema: ver `prompts/enrutador-handoff-a2a-system.md` (a crear).
- Output strict JSON validado por schema antes de invocar el escenario A2A correspondiente.
- Logs de cada decisión guardados en `Pipeline/Logs/enrutador-decisiones-{YYYY-MM}.csv`.

## Casos límite

- **Mensaje ambiguo entre R1 y R2**: si el lead pide "ayuda con IA" sin especificar consultoría vs curso → preguntar (auto-respuesta que pide aclaración) antes de enrutar.
- **Mensaje en idioma raro**: traducir antes de clasificar. No descartar por idioma sin verificar.
- **Mensaje muy corto**: si < 15 palabras y no se puede clasificar con score ≥ 3 → enviar a CEO directamente.

## Mejora continua

- Auditar mensual: ¿cuántos enrutamientos correctos vs corregidos manualmente por la CEO?
- Si tasa de error > 10 % → ajustar el prompt del clasificador.
- Si tasa de error < 3 % consecutivamente 3 meses → este skill puede formar parte de la promoción a Fase 1 del Pdte. Blum.

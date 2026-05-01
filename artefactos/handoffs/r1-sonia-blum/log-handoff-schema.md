# 📊 Esquema log de handoff R1

> El archivo CSV adjunto (`log-handoff.csv`) abre directo en Excel/Sheets como `.xlsx`. El esquema es la fuente de verdad.

## Columnas (en orden)

| Campo | Tipo | Obligatorio | Ejemplo | Notas |
|---|---|---|---|---|
| `handoff_id` | texto único | ✅ | `R1-20260501-130000-lead@x.com` | Generado por Make |
| `fecha_creacion` | datetime ISO | ✅ | `2026-05-01T13:00:00Z` | UTC |
| `ruta` | enum R1-R6 | ✅ | `R1` | Solo R1 en este log |
| `origen_marca` | texto | ✅ | `Sonia Yanez` | |
| `destino_marca` | texto | ✅ | `Blum Digital PR` | |
| `tipo` | texto | ✅ | `Comercial - lead consultoria` | |
| `lead_nombre` | texto | ✅ | `Juan Pérez` | |
| `lead_email` | email | ✅ | `juan@empresa.com` | Validar formato |
| `empresa` | texto | 🟡 | `Acme SA` | |
| `pais` | ISO 2 | 🟡 | `EC` · `ES` · `MX` | |
| `canal_origen` | texto | ✅ | `LinkedIn Sonia` · `Podcast` · `Web` · `Referido` | |
| `mensaje_resumen` | texto ≤ 200 | ✅ | "Interesado en Auditoría ACA…" | Resumen IA del mensaje original |
| `score_ia` | int 1-5 | ✅ | `4` | Calidad del lead estimada por IA |
| `recomendacion_ia` | enum | ✅ | `Express` · `Professional` · `Retencion` · `Descalificar` | |
| `urgencia` | enum | ✅ | `caliente` · `tibio` | Determina SLA |
| `sla_horas` | int | ✅ | `4` (caliente) · `24` (tibio) | |
| `deadline_n1` | datetime ISO | ✅ | `2026-05-01T17:00:00Z` | Fecha límite N1 |
| `owner_n1` | email | ✅ | `owner-blum@dominio.com` | Asignado por Make |
| `estado` | enum | ✅ | `Pendiente` · `En curso` · `Cerrado` · `Vencido N1 - escalado N2` · `Vencido N2 - escalado CEO` · `Descartado` | |
| `fecha_primer_contacto` | datetime ISO | 🟡 | `2026-05-01T15:30:00Z` | Cuando owner contactó al lead |
| `resultado` | enum | 🟡 | `Convertido Express` · `Convertido Professional` · `Convertido Retencion` · `Sin interes` · `Descalificado` · `Sin respuesta` | Final |
| `monto_propuesta_usd` | int | 🟡 | `497` · `1200` · `1500` | Si convertido |
| `notas` | texto libre | 🟡 | "" | |

## Cálculo de KPIs mensuales (fórmulas Excel/Sheets sugeridas)

| KPI | Fórmula |
|---|---|
| Total leads R1 | `=COUNTA(handoff_id) - 1` (excluyendo header) |
| Tasa SLA cumplido | `=COUNTIFS(estado;"<>Vencido*")/COUNTA(handoff_id)` |
| Conversión a Express | `=COUNTIF(resultado;"Convertido Express")/COUNTA(handoff_id)` |
| Conversión a Professional | `=COUNTIF(resultado;"Convertido Professional")` |
| Ingresos generados USD | `=SUMIF(resultado;"Convertido*";monto_propuesta_usd)` |
| Tiempo medio primer contacto (h) | `=AVERAGE(fecha_primer_contacto - fecha_creacion) * 24` |

## Convertir el CSV a XLSX

1. Abrir `log-handoff.csv` en Excel.
2. File → Save As → Excel Workbook (.xlsx).
3. Subir a `Drive/AI-HQ/Pipeline/Handoffs/R1-Sonia-Blum/_plantillas/log-handoff-template.xlsx`.
4. Cada mes, copiar la plantilla → `2026-05-log-handoff.xlsx`, `2026-06-log-handoff.xlsx`, etc.
5. Make puede append filas vía API Sheets si se requiere automatizar (módulo opcional en el blueprint).

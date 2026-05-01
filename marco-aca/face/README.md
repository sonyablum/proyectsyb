# 📐 Modelo FACE™ — Propagación Reputacional Algorítmica

> ⚠️ **Working paper en fase exploratoria — sin validación empírica completa todavía.**
> ⚠️ **No citar sin autorización explícita de Sonia.**

## Versión canónica vigente

- **Documento**: `FACE-Working-Paper-v0.6-corregido_CANONICO_v2.docx` (Drive — id `1eaK7XsaArhbqXcVdB4lhalBcpo16LSPs`)
- **Fecha**: 15-mar-2026
- **Autora**: Sonia Yánez Blum (Observatorio de Reputación Algorítmica)
- **Licencia**: Preprint CC BY-NC-SA 4.0
- **DOI**: 🟡 pendiente Zenodo
- **ORCID en doc**: pendiente actualizar al `0000-0002-6695-8129`

## Qué es

Tercera capa de medición en RR.PP., complementaria a:
- **PESO** (Dietrich, 2014) — tipo de canal
- **Tiers mediáticos** (Shoemaker & Vos, 2009) — alcance/prestigio del medio
- **FACE** (Yánez Blum, 2026) — propagación reputacional en sistemas mediados por IA (ChatGPT, Perplexity, AI Overviews, Gemini, Claude)

## Componentes y pesos provisionales

| ID | Componente | Peso | Mide |
|---|---|---|---|
| **F** | Fuentes | 25% | Orígenes primarios controlados (web, ORCID, repositorios, schema.org) |
| **A** | Amplificadores | 35% | Entidades externas que reproducen (podcasts, newsletters, RRSS, medios) |
| **C** | Catalizadores | 30% | Aceleradores algorítmicos (schema markup, E-E-A-T, backlinks, RAG) |
| **E** | Ecos | 10% | Resultados observables (citaciones LLM, reposts orgánicos, Wikipedia) |

**Score FACE [0,100]** = `0.25·norm(F) + 0.35·norm(A) + 0.30·norm(C) + 0.10·norm(E)` (agregación lineal min-max).

20 indicadores empíricos (5 por componente). Detalle en el WP §3.7.

## Relación con ACA-Score™ (CRÍTICO)

> **FACE y ACA-Score son instrumentos paralelos e independientes. NO se integran en una sola fórmula.**

- **ACA-Score™**: autoridad algorítmica (estructural, condición medible). 4 pilares × 3 KPIs = 12 indicadores.
- **FACE™**: propagación reputacional algorítmica (proceso dinámico de cómo viajan las señales).

Ambos son parte del **Sistema ACA** pero se usan por separado.

## Plan de validación

| Capa | Especificación |
|---|---|
| **Delphi** | n=17 expertos, 3 rondas, Kappa Fleiss ≥0.70. R1 completada feb 2026. R2 en curso Q2 2026. *(Conciliar con `dossier-academico.md` que dice n=18 — verificar fuente correcta)* |
| **Estudio empírico** | N≥100 organizaciones, 24 meses, 50 queries × 4 LLMs (GPT-4o, Gemini 1.5 Pro, Claude 3.5 Sonnet, Perplexity), ≥60% LATAM |
| **Fase piloto** | N=20, 6 meses, 20 queries × 2 LLMs (GPT-4o + Perplexity) |
| **Sub-estudio estabilidad temporal** | 3 mediciones a **7 días** mismo LLM. *(Conciliar con P3 Sondeo 1↔2 que el dossier marca a 10 días)* |
| **Validación psicométrica** | CVR Lawshe (N=12), CFA (CFI≥0.95, RMSEA≤0.06), α≥0.70, ω≥0.75, ICC(2,1)≥0.75 |

## Reglas de uso del modelo

1. ⛔ **No usar para rankings definitivos ni certificaciones** hasta completar validación.
2. ⛔ **No citar públicamente sin OK explícito de Sonia.**
3. ✅ Solo se usa internamente como instrumento de trabajo o en discusiones académicas privadas con Hase / 2 revisores.
4. ✅ Cuando madure y se deposite Zenodo, se podrá ofrecer como producto comercial Blum Digital PR (NO Academia ARP — regla anti-canibalización).
5. 🛑 ARP NO toca FACE™ (junto con ACA-Score™, Reputación Algorítmica, RRPP 6.0®).

## Archivos relacionados en Drive

- `FACE-Working-Paper-v0.6-corregido_CANONICO_v2.docx` — versión vigente
- `FACE-Working-Paper-v0.5.docx` — versión anterior
- `FACE_v04_Reporte_Mejora` — reporte de cambios v0.3→v0.4
- `INSTRUMENTO-FACE-v1.xlsx` — instrumento de medición
- `FACE INSTRUMENTOS-Clase-Sabado15Marzo.xlsx` — material para validación piloto en clase UIDE
- `Formulario-PESO-FACE-Campana360.xlsx` — formulario de aplicación práctica (matriz PESO × FACE)
- `RICFE_Modulo_Avanzado_FACE_ACA_EEAT_2026.docx` — módulo formativo integrado RICFE + FACE + ACA + E-E-A-T
- Carpeta `02-FACE/` y carpeta `FACE FINAL/`

## Pendientes

- [ ] Reconciliar n del Delphi: 17 (FACE WP) vs 18 (dossier académico)
- [ ] Reconciliar ventana del sub-estudio de estabilidad: 7 días (FACE WP) vs 10 días (P3 dossier)
- [ ] Confirmar si el "Delphi R2 cierre 29-abr" del PENDIENTES es del FACE o de otro instrumento
- [ ] Depositar FACE WP en Zenodo cuando Sonia libere la versión definitiva
- [ ] Actualizar ORCID en próxima versión del WP

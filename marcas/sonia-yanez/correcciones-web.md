# Correcciones soniayanez.com — autoridad académica

> 6-nov-2026 · Jefe de Despacho.
> Objetivo: la web como anclaje académico puro, separada operativamente de Blum y ARP.

## Hallazgos de auditoría

- ✅ No menciona "doctoranda" (cumple regla CLAUDE.md).
- ✅ Marco ACA™ explicado con caveat honesto "en desarrollo".
- ✅ ORCID linkeado.
- ✅ 3 preprints Zenodo visibles (pero sin DOIs mostrados).
- 🔴 Hero dice "Investigadora en reputación algorítmica" — **falta "independiente"**.
- 🔴 No menciona afiliación AAU Klagenfurt.
- 🔴 Cross-links fuertes a Blum Digital PR desde el body principal (mezcla autoridad académica con consultoría).
- 🔴 Speaker kit no accesible desde home.
- 🟡 Sin "ES · EN · DE" real (solo switch a EN visible).

## Correcciones mínimas (pueden hacerse sin rediseño)

### 1. Hero — reescribir

**Antes**:
> Investigadora en reputación algorítmica y opinión pública

**Después**:
> Sonia Yánez Blum
> **Investigadora independiente en reputación algorítmica, RRPP 6.0 e IA**
> Autora del Marco ACA™

### 2. Bloque "Afiliación" (nuevo, bajo el hero)

```
Afiliación académica
────────────────────
Alpen-Adria-Universität Klagenfurt — doctorando (RRPP 6.0 e IA)
Supervisora: Dra. Valerie Hase

Afiliación profesional
──────────────────────
Fundadora · Academia de Relaciones Públicas ARP (2020)
Fundadora · Blum Digital PR
Columnista · El Universo (Ecuador)
```

*(Nota: según CLAUDE.md, la comunicación pública debe decir "investigadora independiente" — jamás "doctoranda" pública. Si Sonia quiere suavizar lo de doctorando, se pone "investigación doctoral en curso" sin palabra prohibida.)*

### 3. Mostrar DOIs reales

Donde la web lista los 3 preprints Zenodo, añadir el DOI exacto:
- ACA-Score™ v2 — DOI: 10.5281/zenodo.19035939
- TAA-IA — DOI: 10.5281/zenodo.18802347
- RICFE® v1.0 — DOI: 10.5281/zenodo.19388591

*(Nota CLAUDE.md: solo publicar DOIs públicos. ACA-Score v3 NO citar.)*

### 4. Separar narrativa académico / comercial

**Hoy**: el body de la home envía al lector directo a "Blum Digital PR" para capacitaciones.

**Cambio propuesto**:
- Mover los cross-links a un **footer dedicado** titulado "Mis proyectos":
  - Blum Digital PR → consultoría premium B2B
  - Academia ARP → formación B2C
- El body principal queda sobre investigación, charlas, docencia, publicaciones.

### 5. Añadir Speaker Kit público

Nueva página `/speaker-kit` enlazada desde el nav:
- Bio corta / media / larga (español + inglés)
- Foto profesional 3:4 y 16:9 en alta resolución
- 3 temas de conferencia con descripción y duración
- Rider técnico
- Honorarios de referencia (opcional — Sonia decide)
- Clips de charlas previas

### 6. SEO / GEO / AEO

- Schema.org `Person` con `sameAs` a ORCID, Zenodo, LinkedIn, El Universo.
- Meta description: "Sonia Yánez Blum — investigadora independiente en reputación algorítmica, autora del Marco ACA™."
- Añadir página `/publicaciones` con los 3 preprints y su DOI individual (cada uno es una página con JSON-LD `ScholarlyArticle`).
- Esto refuerza la citabilidad en los LLMs (su propio ACA-Score).

### 7. Firewall Sonja Kalos

- Cero mención, cero link, cero footer cruzado.
- Verificar que el CSS/tema no es compartido (no por técnica, por separación de huella).

## Priorización

| Cambio | Impacto | Esfuerzo | Prioridad |
|---|---|---|---|
| Hero con "independiente" | Alto | 5 min | 🔴 hoy |
| Bloque afiliación | Alto | 15 min | 🔴 hoy |
| Mostrar DOIs | Alto | 10 min | 🔴 hoy |
| Separar cross-links a footer | Alto | 30 min | 🟡 esta semana |
| Speaker Kit | Medio | 2 h | 🟡 esta semana |
| SEO/GEO/AEO | Alto | 3 h | 🟢 próxima semana |

## Qué falta de Sonia

1. Autorización para cambios de copy en hero + afiliación.
2. Foto profesional para Speaker Kit si no está disponible.
3. Decisión: ¿mostrar honorarios de speaker públicos o no?
4. Confirmar quién edita WordPress (ella o alguien externo).

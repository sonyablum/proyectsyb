# 🔁 Propagación de decisiones de marca al ecosistema

> Una decisión de la CEO no vale donde se tomó. Vale en todas las superficies que la ejecutan.
> Este documento define cómo se propaga, quién la aplica y cómo se verifica que se aplicó.

## Por qué existe

El 12 de julio de 2026 la CEO decidió que solo `RICFE™` y `HACERP™` llevan ™. La decisión quedó
escrita en el Documento Madre de ARP y no viajó a ninguna otra parte.

Dieciocho días después, el ecosistema seguía operando con la regla contraria:

| Superficie | Estado el 30-07-2026 |
|---|---|
| Skills del AI HQ | 46 de 96 usaban símbolos prohibidos: 92 símbolos de registro y unos 250 de marca no registrada |
| `gobernanza/anti-canibalizacion.md` | ACA-Score, FACE y ACA Seal marcados como no registrados; RICFE marcado como registrado |
| `Blumiapr/content/SERVICIOS-PRODUCTOS-BLUM-v2.md` | Autorizaba el símbolo en ACA y ACA-Score «en material comercial» |
| Los 5 guardianes | Aplicaban la regla contraria **como gate de publicación** |

El caso agravante: `guardian-marca-sonia-yanez` contenía una «DECISIÓN BLINDADA (jun 2026)»
—anterior— que seguía activa y bloqueaba la de julio. Una decisión derogada seguía gobernando.

Y `articulos-blog-blum` instruía marcarlas **todas hasta auditar registros**: una medida provisional
que se volvió permanente porque nadie tenía el encargo de cerrarla.

**Consecuencia práctica:** durante dieciocho días, todo el contenido publicado por el ecosistema
afirmó derechos de marca inexistentes sobre siete signos no registrados. No por desacuerdo, sino
porque no había un mecanismo de propagación.

## Qué es una decisión vinculante

Una decisión de la CEO sobre naming, símbolos de marca, frontera entre marcas, precios públicos,
credenciales o territorio de producto. Se reconoce porque **contradice o restringe algo que el
ecosistema ya está ejecutando**.

No lo es una preferencia de estilo de una pieza concreta, ni una instrucción de tarea.

## Protocolo de propagación

Al recibir una decisión vinculante, **en la misma sesión**:

**1 · Registrarla aquí.** En la tabla de decisiones vigentes, con fecha. Si deroga una anterior, la
anterior se marca DEROGADA con la fecha y la que la sustituye — nunca se borra, para que su rastro
sea auditable.

**2 · Barrer las cuatro superficies.** Ninguna es opcional:

| Superficie | Dónde | Riesgo si se omite |
|---|---|---|
| Gobernanza | `proyectsyb/gobernanza/` | La regla escrita contradice a la CEO |
| Skills del AI HQ | `iapr/skills/` + instalación local | Se ejecuta la regla vieja en cada pieza |
| Activos públicos | `Blumiapr/content/`, webs, catálogos | Sale publicado |
| Documentos madre | Drive: Documento Madre, mapeos | Fuente de verdad divergente |

**3 · Empezar por los guardianes.** Son gate de publicación: mientras apliquen la regla vieja,
*rechazan activamente* las piezas que cumplen la nueva. Un guardián desactualizado no es un
documento obsoleto — es un bloqueo que revierte la decisión pieza a pieza.

**4 · Buscar la regla, no la palabra.** Hay líneas que *legislan* sobre lo decidido
(«solo ™, nunca ®», «TODOS con ™ hasta auditar»). Limpiarlas mecánicamente destruye la norma y
deja el archivo sin regla. Se reescriben con el texto canónico, una por una.

**5 · Verificar y dejar rastro.** Ejecutar la auditoría, adjuntar el conteo al PR y anotar aquí la
fecha de propagación.

## Regla de versionado de skills

**Todo skill propio vive en `iapr/skills/`.** Sin excepción.

Un skill que solo existe en la instalación local no es revisable, no es recuperable, no admite PR
y muere con el entorno. El 30-07-2026 había 28 en esa situación —incluidos los cinco guardianes,
que son precisamente los que ejercen de gate.

Los skills de Anthropic (`docx`, `pdf`, `pptx`, `xlsx`, `canvas-design`, `brand-guidelines`,
`skill-creator`, `theme-factory`, `web-artifacts-builder`, `mcp-builder`, `doc-coauthoring`,
`internal-comms`, `algorithmic-art`) no se versionan: no son propios y se actualizan solos.

**Dirección de sincronización:** la instalación local es lo que se ejecuta, y por tanto la fuente
de verdad operativa. Antes de sincronizar hacia el repo, comprobar que ningún archivo del repo sea
más reciente (campo `version` / `actualizado` del frontmatter). Si lo es, resolver a mano.

## Auditoría

`iapr/scripts/auditoria-marcas.py` verifica la regla de símbolos en cualquier árbol:

```bash
python3 scripts/auditoria-marcas.py skills/ --check    # informa, no modifica; sale 1 si hay hallazgos
python3 scripts/auditoria-marcas.py skills/            # aplica la corrección
```

Respeta marcas de terceros (`Just Connecting™`) y no toca las líneas normativas: las lista para
reescritura manual.

**Cadencia:** al propagar cualquier decisión, y en la rutina mensual de mantenimiento del AI HQ
(primer viernes, junto a `detector-skills-faltantes`).

## Decisiones vinculantes vigentes

| Fecha | Decisión | Estado | Propagada |
|---|---|---|---|
| 12-07-2026 | **Símbolos de marca.** Solo `RICFE™` y `HACERP™` llevan ™. ACA, Marco ACA, ACA-Score, FACE, TAA, ACA Seal, GEAC, RRPP 6.0 y «Reputación Algorítmica» no están registradas: sin símbolo. Nunca ® en ninguna marca. | **Vigente** | 30-07-2026 |
| 30-07-2026 | **Frontera de formación.** La formación in-house en gobernanza y reputación algorítmica es producto premium de Blum. El curso online general para comunicadores es Academia ARP. El criterio es el formato y el nivel, no el tema. | **Vigente** | 30-07-2026 |
| 30-07-2026 | **Vía académica.** El diseño de syllabus y módulos para universidades es una tercera vía con criterio propio, fuera de la frontera in-house/online. | **Vigente** | Criterio de marca pendiente |
| jun-2026 | Símbolos: «las marcas no están registradas → usar solo ™». | **DEROGADA** por la del 12-07-2026 | 30-07-2026 |

## Qué sigue abierto

- **ARP-C04 y ARP-C05** — figuran en el catálogo de ARP sin que conste que existan como producto.
  Sin marca asignada hasta confirmarlo.
- **Vía académica** — falta definir marca, precio y límites.
- **`iapr/docs/MAPEO-FINAL-HQ-JUL2026.md`** — lista el curso de reputación algorítmica como
  «ARP-C02, 197–247 USD, asincrónico». El real cuesta 99 USD e incluye sesión en vivo mensual.
- **`marcas/academia-arp/README.md`** — el catálogo figura «por construir» con el curso vendiéndose.

# 🏛 Capa de gobernanza — Grupo Sonia Yánez Blum

## Las 3 capas

```
   CEO (Sonia, humana)               decide y envía al exterior
        ▲
   JEFE DE DESPACHO (Claude)         orquesta · reporta · coherencia · A2A · SLA
        ▲
   4 PRESIDENTES IA (asesores)       recomiendan por marca · NUNCA deciden
        ▲
   6 SUBAGENTES FUNCIONALES          ejecutan: mkt · ventas · pr-medios · cfo
   (compartidos entre marcas)        automatizaciones · congresos-académicos
```

## Reglas de capa

1. **Subagente** ejecuta una función técnica concreta. Reporta al Presidente que lo invoca.
2. **Presidente** es una IA con expertise específico por marca. Sintetiza, recomienda, presenta opciones al Jefe de Despacho. **Nunca decide** unilateralmente. Es dueño de los handoffs entrantes a su marca.
3. **Jefe de Despacho** orquesta entre los 4 Presidentes, mantiene la coherencia cross-brand, vigila los SLA del Sistema A2A, prepara el paquete de decisión para la CEO. **Nunca envía nada al exterior sin OK** de Sonia.
4. **CEO (Sonia)** decide, autoriza envíos externos, y vigila las reglas inquebrantables del grupo.

## Documentos de esta carpeta

| Archivo | Función |
|---|---|
| `presidentes/sonia-yanez.md` | Mandato del Presidente de la marca personal académica |
| `presidentes/blum-digital-pr.md` | Mandato del Presidente de Blum (consultoría B2B) |
| `presidentes/academia-arp.md` | Mandato del Presidente de Academia ARP (educativa) |
| `presidentes/sonja-kalos.md` | Mandato del Presidente del silo Sonja Kalos |
| `sistema-a2a.md` | Las 6 rutas A2A entre marcas + 0 hacia Sonja Kalos |
| `sla-handoff.md` | Matriz de SLA por tipo de handoff (N1 Owner / N2 Pdte / N3 CEO) |
| `anti-canibalizacion.md` | Las 3 reglas duras que protegen el posicionamiento de cada marca |

## Cuándo invocar a un Presidente

Desde el Jefe de Despacho:
> "Activa Pdte. Blum para evaluar la propuesta UIDE Professional"
> "Pdte. Sonia recomienda enfoque para la ponencia Congreso H"

Cada Presidente lee:
1. Su brief operativo (`marcas/{marca}/`)
2. Los activos intelectuales relevantes (`marco-aca/`, dossier académico)
3. Las reglas de su marca + reglas inquebrantables del grupo
4. El input específico que el Jefe de Despacho le pasa

Devuelve: **opciones priorizadas + recomendación + lo que necesita de la CEO**.

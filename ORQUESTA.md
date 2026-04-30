# 🎼 Orquesta Sonia Yánez AI HQ

Director: **Sonia Yánez Blum** — RRPP 6.0, IA y Reputación Algorítmica.
Jefe de Despacho: **Claude (este agente)**.
Sede: Klagenfurt, Austria → Latinoamérica.

## Mapa de la orquesta

```
SONIA (Directora)
   │
   └── JEFE DE DESPACHO (Claude)
         │
         ├── agente-marketing
         ├── agente-ventas
         ├── agente-pr-medios
         ├── agente-cfo
         ├── agente-automatizaciones
         └── agente-congresos-academicos
```

Cada agente tiene:
- **prompt-system** en `/agentes/{nombre}.md`
- **skills** que ejecuta → `/skills/`
- **artefactos** que produce → `/artefactos/`
- **rutinas** recurrentes → `/routines/`

## Marco conceptual

Todo entregable se ancla al **Marco ACA™** (Auditoría de Comunicación Algorítmica) y al protocolo **IA-Ethics**.
Documentos base en `/marco-aca/` — ⚠️ pendiente subir versión actualizada (ver `PENDIENTES.md`).

## Servicios activos

| Servicio | Precio | Skill |
|---|---|---|
| Auditoría ACA™ Express | $497 | `skills/auditoria-aca-express.md` |
| Auditoría ACA™ Professional | $1,200 | `skills/auditoria-aca-professional.md` |
| Retención mensual | $1,500/mes | `skills/retencion-mensual.md` |

## Clientes activos

- **Amcham Guayaquil** — 8 chats WhatsApp activos
- **SFIC-Rina**
- **UIDE-Cynthia**

Fichas en `/artefactos/fichas-clientes/` (pendiente subir ZIP a Drive workspace `soniayanezblum@gmail.com`).

## Cómo invocar un agente

En conversación con el Jefe de Despacho:
> "Activa agente-ventas para preparar propuesta UIDE Professional"

El Jefe de Despacho lee `/agentes/agente-ventas.md`, ejecuta la skill correspondiente y devuelve el artefacto listo.

## Estado actual

Ver `PENDIENTES.md` para bloqueantes y prioridades de la semana.

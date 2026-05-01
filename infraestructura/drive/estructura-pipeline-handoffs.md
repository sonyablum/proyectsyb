# 📁 Estructura Drive — Pipeline de Handoffs

> Workspace: `soniayanezblum@gmail.com`. Crear esta estructura **antes** de importar el escenario Make R1.

```
AI-HQ/
├── Pipeline/
│   ├── Handoffs/
│   │   ├── R1-Sonia-Blum/
│   │   │   ├── 2026-05/         ← carpeta por mes
│   │   │   ├── 2026-06/
│   │   │   └── _plantillas/     ← log .xlsx, emails
│   │   ├── R2-Sonia-ARP/
│   │   ├── R3-Blum-Sonia/
│   │   ├── R4-Blum-ARP/
│   │   ├── R5-ARP-Sonia/
│   │   └── R6-ARP-Blum/
│   ├── Logs/
│   │   ├── 2026-05-handoffs-mensual.xlsx
│   │   └── _plantilla-log-mensual.xlsx
│   └── Reportes/
│       └── 2026-05-reporte-A2A.md
└── Auditoria/
    ├── SLA-incumplidos/
    └── Canibalizacion-detectada/
```

## Permisos por carpeta

| Carpeta | Acceso |
|---|---|
| `AI-HQ/` | Sonia + Jefe de Despacho (acceso técnico Make) |
| `Pipeline/Handoffs/R*-` | Solo Pdte. dueño de la ruta + Sonia |
| `Pipeline/Logs/` | Sonia + Jefe de Despacho (lectura ampliada para reportes) |
| `Auditoria/` | Solo Sonia + Jefe de Despacho |

## Reglas

1. **Nada compartido público**: ningún "anyone with the link". Solo invitados específicos.
2. **No exportar carpetas masivas** sin OK CEO.
3. **Audit log de Drive activado** en workspace.
4. **Auditoría mensual**: revisar permisos en `Pipeline/Handoffs/*` el primer lunes de cada mes (ver `skills/seguridad/datos-sensibles-gdpr.md`).
5. **Carpeta Sonja Kalos**: NO existe en este árbol. Vive en su propio Drive separado (firewall técnico).

## Cómo crearla (paso a paso)

1. Abrir Drive de `soniayanezblum@gmail.com`.
2. New → Folder → `AI-HQ`.
3. Dentro de `AI-HQ`, crear `Pipeline` y `Auditoria`.
4. Dentro de `Pipeline`, crear `Handoffs`, `Logs`, `Reportes`.
5. Dentro de `Handoffs`, crear las 6 carpetas R1-R6.
6. Dentro de cada `R*-`, crear `_plantillas/` y `2026-05/`.
7. Subir las plantillas (log .xlsx, emails .md) a `_plantillas/` de R1.
8. Configurar Make con la ruta `AI-HQ/Pipeline/Handoffs/R1-Sonia-Blum/{{YYYY-MM}}/`.

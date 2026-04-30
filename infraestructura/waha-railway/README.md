# WAHA en Railway — Deploy guide

WAHA = WhatsApp HTTP API (open source). Despliega un endpoint HTTP que envía/recibe mensajes WhatsApp.

## Prerrequisitos
- Cuenta Railway (https://railway.app) con plan Hobby ($5/mo) o superior.
- Número WhatsApp dedicado (NO el personal de Sonia).
- Acceso al móvil para escanear QR la primera vez.

## Deploy paso a paso (viernes 9:30 AM)

### 1. Crear proyecto en Railway
1. Login Railway → **New Project** → **Deploy from GitHub repo** → seleccionar este repo (`sonyablum/proyectsyb`).
2. Cuando pregunte root: dejar `/`. Railway detectará el `Dockerfile` en `infraestructura/waha-railway/`.
3. Si no auto-detecta: Settings → Root Directory → `infraestructura/waha-railway`.

### 2. Variables de entorno (Settings → Variables)
Copiar de `.env.example` y completar:

```
WAHA_API_KEY=                # cadena aleatoria larga (genera con: openssl rand -hex 32)
WHATSAPP_DEFAULT_ENGINE=WEBJS
WHATSAPP_HOOK_URL=           # URL del webhook Make (la pegamos después del paso 5)
WHATSAPP_HOOK_EVENTS=message,session.status
WAHA_DASHBOARD_USERNAME=sonia
WAHA_DASHBOARD_PASSWORD=     # contraseña fuerte
TZ=Europe/Vienna
```

### 3. Deploy
1. Push al branch `claude/multi-agent-pr-agency-mDAzQ` activa el build.
2. Railway crea servicio en ~3 min.
3. Settings → Networking → **Generate Domain** → guarda la URL pública (ej: `waha-syab.up.railway.app`).

### 4. Health check
```
curl https://{tu-dominio}/api/health \
  -H "X-Api-Key: ${WAHA_API_KEY}"
```
Debe responder `{"status":"UP"}`.

### 5. Iniciar sesión WhatsApp
1. Abrir `https://{tu-dominio}/dashboard` → login con `WAHA_DASHBOARD_USERNAME/PASSWORD`.
2. Crear sesión `default` → escanear QR con WhatsApp del número dedicado.
3. Estado debe pasar a `WORKING`.

### 6. Conectar webhook a Make
1. En Make: crear escenario nuevo → módulo "Custom webhook" → copiar URL.
2. Volver a Railway → Variables → `WHATSAPP_HOOK_URL` = URL del webhook → redeploy.
3. Enviar mensaje de prueba al WhatsApp → debe llegar a Make.

## Troubleshooting
| Síntoma | Causa probable | Fix |
|---|---|---|
| Build falla | Falta Dockerfile | Verificar Root Directory |
| QR no aparece | Sesión bloqueada | Reiniciar servicio en Railway |
| Webhook no dispara | URL mal puesta | Probar curl manual al hook |
| 401 en API | `X-Api-Key` faltante | Incluir en cada request |

## Costos esperados
- Railway Hobby: $5/mo + uso (~$1-3/mo extra).
- Total: **~$6-8/mes**.

## Seguridad
- `WAHA_API_KEY` y `WAHA_DASHBOARD_PASSWORD`: solo en Railway Variables, NUNCA en repo.
- Restringir webhook a IPs Make si se requiere endurecimiento.
- Backup periódico de sesiones en Railway Volumes (recomendado mes 2).

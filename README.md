# 🩺 Symptom Tracker - Monorepo

Este proyecto permite registrar y hacer seguimiento de síntomas de salud. Está estructurado como un monorepo y utiliza tecnologías modernas tanto para el frontend como el backend, incluyendo contenedores Docker para facilitar el despliegue.

---

## 📦 Tecnologías utilizadas

- **Frontend**: Probablemente React o similar (basado en estructura de monorepo).
- **Backend**: Node.js con Express o NestJS.
- **Base de datos**: Se infiere uso de PostgreSQL o MongoDB (según configuración en `docker-compose.yml`).
- **Contenedores**: Docker y Docker Compose.
- **Control de versiones**: Git.
- **Orquestación**: `docker-compose.yml` define múltiples servicios.
- **Plataforma en la nube (sugerida)**: Puede desplegarse fácilmente en plataformas como:
  - **Render.com**
  - **Heroku**
  - **Railway**
  - **AWS ECS o Lightsail**
  - **Azure Web Apps**
  - **Google Cloud Run**

---

## 🚀 ¿Cómo implementar este proyecto?

### 🔧 Requisitos previos

- Docker y Docker Compose instalados en tu máquina.
- Node.js (si se desea ejecutar localmente sin Docker).
- Acceso a un proveedor de nube si deseas desplegarlo remotamente.

---

### 🛠️ Paso a paso para ejecución local

1. **Clonar el repositorio**
   ```bash
   git clone <URL-del-repositorio>
   cd symptom-tracker-monorepo

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
   
2. **Construir e iniciar los contenedores**
   ```bash
   docker-compose up --build

3. **Acceder a la aplicación**
- **Frontend:** http://localhost:3000
- **Backend API:** http://localhost:5000 (puede variar)
- **Base de datos:** configurada internamente (puede usarse Adminer o pgAdmin si está incluido)

## ☁️ Despliegue en la nube

Puedes seguir los siguientes pasos si usas plataformas como **Render**, **Railway** o **Heroku**:

1. Crear cuenta y nuevo servicio desde un repositorio Git
2. Configurar variables de entorno necesarias (como DB_URL, JWT_SECRET, etc.)
3. Asegúrate de que el archivo docker-compose.yml esté en la raíz
4. Elige los puertos adecuados (por ejemplo, 80 o 443)
5. Desplegar y monitorear desde el panel de la nube

## 🧪 Scripts típicos (si se definen en cada módulo)
 ```bash
# Instalar dependencias
npm install

# Iniciar servidor de desarrollo
npm run dev

# Compilar producción
npm run build

## 📁 Estructura típica del monorepo
```bash
symptom-tracker-monorepo/
├── apps/
│   ├── frontend/        # Interfaz del usuario
│   └── backend/         # Lógica del servidor / API
├── docker-compose.yml   # Orquestación de servicios
├── package.json         # Dependencias generales (si aplica)
└── README.md            # Documentación del proyecto

Nota: Explora los subdirectorios apps/, services/ o packages/ para más package.json individuales si estás editando o ampliando este proyecto.

## 📄 Licencia

Este proyecto está licenciado bajo MIT o la licencia definida por el autor original.

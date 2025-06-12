# 🩺 Symptom Tracker - Monorepo

Este proyecto permite registrar y hacer seguimiento de síntomas de salud. Está estructurado como un monorepo y utiliza tecnologías modernas tanto para el frontend como el backend, incluyendo contenedores Docker para facilitar el despliegue.

---

## 🚀 Tecnologías utilizadas

| Componente     | Tecnología         |
|----------------|--------------------|
| Backend        | Node.js + Express  |
| Base de datos  | MongoDB            |
| Frontend       | Vue.js + Vite      |
| Contenedores   | Docker, Docker Compose |
| Servidor Web   | Nginx              |
| Nube           | Microsoft Azure    |

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
- **patients-service**: http://localhost:3001
- **symptoms-service**: http://localhost:3002
- **frontend Vue.js**: http://localhost:8080
- **api-gateway**:  http://localhost:3000

## ☁️ Despliegue en la nube

La aplicación fue desplegada en **Azure**, usando:

- **Azure App Service** para los microservicios Node.js
- **Azure Cosmos DB (API MongoDB)** o una máquina virtual con MongoDB para persistencia de datos
- **Azure Storage + CDN** o App Service para alojar el frontend

## 🧪 Scripts típicos (si se definen en cada módulo)

```bash
# Instalar dependencias
npm install

# Iniciar servidor de desarrollo
npm run dev

# Compilar producción
npm run build
```

## 📁 Estructura del proyecto

```text
SYMPTOM-TRACKER-MONOREPO/
├── .github/
│   └── workflows/
│       └── deploy.yml
├── client/
│   └── vue-symptom-app/
│       ├── node_modules/
│       ├── src/
│       ├── .env.development
│       ├── .env.production
│       ├── Dockerfile
│       ├── index.html
│       ├── nginx.conf
│       ├── package-lock.json
│       ├── package.json
│       └── vite.config.js
├── node_modules/
│   ├── cors/
│   ├── object-assign/
│   └── vary/
├── services/
│   ├── docker-compose.yml
│   ├── package-lock.json
│   └── package.json
└── README.md





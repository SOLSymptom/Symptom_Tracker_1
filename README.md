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
- **Frontend:** http://localhost:3000
- **Backend API:** http://localhost:5000 (puede variar)
- **Base de datos:** configurada internamente (puede usarse Adminer o pgAdmin si está incluido)

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

## 📁 Estructura típica del monorepo

```bash
symptom-tracker-monorepo/
├── apps/
│   ├── frontend/        # Interfaz del usuario (React, Next.js u otro)
│   └── backend/         # Lógica del servidor / API (Node.js, Express, etc.)
├── docker-compose.yml   # Orquestación de servicios (base de datos, backend, etc.)
├── package.json         # Dependencias generales del monorepo (opcional)
└── README.md            # Documentación del proyecto
```

## 📄 Licencia

Este proyecto está licenciado bajo MIT o la licencia definida por el autor original.


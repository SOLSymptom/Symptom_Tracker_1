# Etapa de construcción
FROM node:18-slim AS build-stage
WORKDIR /app

# Instalar dependencias del sistema necesarias
RUN apt-get update && apt-get install -y curl && rm -rf /var/lib/apt/lists/*

# Configurar npm para mejor estabilidad
RUN npm config set registry https://registry.npmmirror.com \
  && npm config set fetch-retries 5 \
  && npm config set fetch-retry-mintimeout 2000 \
  && npm config set fetch-retry-maxtimeout 10000

# Copiar package.json y package-lock.json
COPY package*.json ./

# Instalar solo dependencias de producción (omite dev para no llevar vite)
RUN npm ci --omit=dev

# Copiar el resto de la app
COPY . .

# Variables de entorno para Vite
ARG VITE_API_URL
ENV VITE_API_URL=$VITE_API_URL

# Dar permisos de ejecución a vite y compilar
RUN chmod +x node_modules/.bin/vite
RUN node_modules/.bin/vite build

# Etapa de producción
FROM nginx:stable-alpine AS production-stage

# Copiar archivos construidos al Nginx
COPY --from=build-stage /app/dist /usr/share/nginx/html

# Copiar configuración custom de nginx
COPY nginx.conf /etc/nginx/conf.d/default.conf

EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
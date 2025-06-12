# Etapa de build
FROM node:18-alpine AS build-stage

WORKDIR /app

# Copiar archivos necesarios
COPY package*.json ./

# Instalar dependencias (instala Vite incluido en devDependencies)
RUN npm install

# Copiar el resto del código fuente
COPY . .

# Compilar la aplicación con Vite
RUN npx vite build
# Etapa de construcción
FROM node:18-alpine AS build-stage
WORKDIR /app

# Configurar NPM con mirror confiable y reintentos automáticos
RUN npm config set registry https://registry.npmmirror.com \
  && npm config set fetch-retries 5 \
  && npm config set fetch-retry-mintimeout 2000 \
  && npm config set fetch-retry-maxtimeout 10000

# Copiar archivos necesarios para instalar dependencias
COPY package*.json ./

# Instalar dependencias sin las de desarrollo
RUN npm ci --omit=dev

# Copiar el resto del código fuente
COPY . .

# Variable de entorno y argumento para Vite
ARG VITE_API_URL
ENV VITE_API_URL=$VITE_API_URL

# Asegurarse de que vite esté disponible y compilar el proyecto
RUN chmod +x node_modules/.bin/vite && npm run build

# Etapa de producción con nginx
FROM nginx:stable-alpine AS production-stage

# Copiar el resultado del build al directorio público de nginx
COPY --from=build-stage /app/dist /usr/share/nginx/html

# Copiar configuración personalizada de nginx
COPY nginx.conf /etc/nginx/conf.d/default.conf

EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
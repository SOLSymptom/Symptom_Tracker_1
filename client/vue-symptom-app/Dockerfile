# Etapa de construcción
FROM node:18-alpine AS build-stage
WORKDIR /app

# Usar mirror confiable y npm ci para builds consistentes
RUN npm config set registry https://registry.npmjs.org/

# Copiar solo lo necesario para instalar
COPY package*.json ./

# Usar ci para builds más rápidos y consistentes
RUN npm ci --omit=dev

# Copiar el resto del código
COPY . .

# Variable de entorno y ARG para Vite
ARG VITE_API_URL
ENV VITE_API_URL=$VITE_API_URL

# Asegurarse de que vite esté disponible y compilar
RUN chmod +x node_modules/.bin/vite && npm run build

# Etapa de producción con nginx
FROM nginx:stable-alpine AS production-stage

# Copiar el resultado del build
COPY --from=build-stage /app/dist /usr/share/nginx/html

# Copiar configuración personalizada de nginx
COPY nginx.conf /etc/nginx/conf.d/default.conf

EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
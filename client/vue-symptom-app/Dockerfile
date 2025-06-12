# Etapa de construcción
FROM node:18-alpine AS build-stage
WORKDIR /app

COPY package*.json ./
RUN npm install

COPY . .

# Solo necesitas un ARG y ENV ahora
ARG VITE_API_URL
ENV VITE_API_URL=$VITE_API_URL

RUN chmod +x node_modules/.bin/vite && npm run build

# Etapa de producción con nginx
FROM nginx:stable-alpine AS production-stage
COPY --from=build-stage /app/dist /usr/share/nginx/html
COPY nginx.conf /etc/nginx/conf.d/default.conf

EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
# symptom-tracker-monorepo/client/vue-symptom-app/Dockerfile
FROM node:18-alpine AS build-stage
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
# VITE_* variables can be passed as build args if needed for production
ARG VITE_PATIENTS_SERVICE_URL
ARG VITE_SYMPTOMS_SERVICE_URL
ENV VITE_PATIENTS_SERVICE_URL=$VITE_PATIENTS_SERVICE_URL
ENV VITE_SYMPTOMS_SERVICE_URL=$VITE_SYMPTOMS_SERVICE_URL
RUN npm run build

FROM nginx:stable-alpine AS production-stage
COPY --from=build-stage /app/dist /usr/share/nginx/html
COPY nginx.conf /etc/nginx/conf.d/default.conf
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
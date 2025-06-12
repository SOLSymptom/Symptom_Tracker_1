FROM node:18-alpine

# Establece la carpeta de trabajo
WORKDIR /app

# Copia solo los archivos necesarios para instalar dependencias
COPY package*.json ./

# Configura temporalmente un mirror de NPM para evitar errores 503
RUN npm config set registry https://registry.npmjs.org/ \
  && npm install --omit=dev \
  && npm cache clean --force

# Copia el resto de los archivos del proyecto
COPY . .

# Establece variables de entorno
ENV PORT=3001

# Expone el puerto del servicio
EXPOSE 3001

# Comando por defecto al iniciar el contenedor
CMD ["npm", "start"]

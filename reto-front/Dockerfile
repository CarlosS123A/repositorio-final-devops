# Usar una imagen base de Node.js
FROM node:16-alpine

# Establecer el directorio de trabajo en el contenedor
WORKDIR /usr/src/app

# Copiar el package.json y package-lock.json al contenedor primero para aprovechar la caché
COPY package*.json ./

# Instalar las dependencias
RUN npm install

# Copiar el resto del código de la aplicación al contenedor
COPY . .

# Exponer el puerto en el que la aplicación va a correr
EXPOSE 3000

# Comando para ejecutar la aplicación
CMD ["npm", "start"]

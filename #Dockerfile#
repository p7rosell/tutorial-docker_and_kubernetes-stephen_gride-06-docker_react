# Video 90
# Vamos a generar 2 imagenes base, la de node:alpine y nginx

### ==================================================== ###
###                 Specify a base image                 ###
### ==================================================== ###
FROM node:alpine

### ==================================================== ###
###               Install some dependencies              ###
### ==================================================== ###
WORKDIR '/app'

COPY package.json ./
RUN npm install
COPY ./ ./

RUN npm run build


### ==================================================== ###
###                 Specify a base image                 ###
### ==================================================== ###
FROM nginx

### ==================================================== ###
###               Install some dependencies              ###
### ==================================================== ###
# Copiamos la carpeta del contenedor "node:alpine a nginx"
COPY --from=0 /app/build /usr/share/nginx/html

### ==================================================== ###
###               Install some dependencies              ###
### ==================================================== ###
# Con Nginx no hace falta iniciar nada
# El puerto de nginx es el 80

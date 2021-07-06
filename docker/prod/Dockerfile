# Aqui van las instrucciones para crear una imagen de docker

# Le digo a docker que version de node voy a usar
FROM node:12-slim as Build

# Le digo a docker donde van a estar las carpetas/proyectos que voy a usar dentro de mi container AHORA ES LA CARPETA RAIZ
WORKDIR /usr/src/app 

# Decirle a docker como levantar mi proyecto de node

# Copiar el pacakge json y ponerlo en la carpeta raiz del contenedor
COPY package.json package-lock.json ./

ENV NODE_ENV=production

# Una vez copiado el package json ahora se instalan las dependencias
RUN npm ci --production && npm cache clean --force

# Copiar la todo en donde estas parado a la raiz del contenedor
COPY . .

ENTRYPOINT [ "node", "index.js" ]
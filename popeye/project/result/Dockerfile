FROM node:12-alpine

USER root
WORKDIR /home/app
COPY package*.json ./
RUN npm install
COPY . .

EXPOSE 80

CMD ["node", "server.js"]
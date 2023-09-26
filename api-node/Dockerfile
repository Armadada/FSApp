FROM node:alpine3.18 AS base

WORKDIR /usr/app/src/

COPY package*.json .

RUN npm install

COPY . .

CMD ["node", "./src/index.js"]


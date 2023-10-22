FROM node:alpine

WORKDIR /usr/src/app

COPY package*.json ./

RUN npm install

RUN npm install -g npm

COPY . .

EXPOSE 5000

CMD ["npm", "start"]

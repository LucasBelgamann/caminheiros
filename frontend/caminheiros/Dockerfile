FROM node:16-alpine

WORKDIR /app-front

COPY package.json ./

RUN npm install

COPY . .

CMD ["npm", "run", "dev"]

FROM node:20-alpine

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY . .

EXPOSE 3001

CMD ["npx", "json-server", "--watch", "db.json", "--host", "0.0.0.0", "--port", "3001"]
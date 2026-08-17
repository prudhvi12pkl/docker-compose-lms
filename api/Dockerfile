FROM node:16-alpine

WORKDIR /app

COPY package*.json ./
RUN npm install

RUN npm install prisma@5.22.0 @prisma/client@5.22.0 --save

COPY . .

RUN npx prisma generate
RUN npm run build

EXPOSE 8080

CMD ["sh", "-c", "npx prisma db push && node build/index.js"]


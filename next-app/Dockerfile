FROM node:20-alpine as build

WORKDIR /app

COPY . .
RUN npm ci --silent
RUN npm run build

EXPOSE 3000

CMD ["npm", "start"]

FROM node:latest AS build

WORKDIR /app

COPY . .

RUN npm install
RUN npm run build

FROM nginx:alpine
COPY --from=build /app/out /usr/share/nginx/html

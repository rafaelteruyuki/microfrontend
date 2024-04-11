FROM node:20-alpine as build

WORKDIR /app

COPY . .

RUN npm ci --silent
RUN npm run build -- --deploy-url /angular/

#Starting NGINX
FROM nginx

COPY ./nginx.conf /etc/nginx/nginx.conf
COPY --from=build /app/dist/angular-app/browser /usr/share/nginx/html


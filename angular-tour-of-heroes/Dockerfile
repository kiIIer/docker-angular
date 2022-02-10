FROM node:17.4.0-alpine3.14 AS build
WORKDIR /app
COPY package*.json .
RUN npm ci
COPY ./ .
RUN npm run build

FROM nginx:1.21.6-alpine
COPY --from=build /app/dist/angular-tour-of-heroes /usr/share/nginx/html

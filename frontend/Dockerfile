FROM node:16 AS build
WORKDIR /bookjuk
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build

FROM nginx:alpine
COPY --from=build /bookjuk/build /usr/share/nginx/html
COPY nginx.conf /etc/nginx/conf.d/default.conf
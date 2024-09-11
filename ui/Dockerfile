FROM node:lts-slim AS build

WORKDIR /app

COPY . .

RUN yarn

RUN yarn build

FROM nginx:1.27.1

WORKDIR /usr/share/nginx/html

RUN rm -rf ./*

COPY --from=build /app/build .
COPY ./nginx.conf /etc/nginx/conf.d/default.conf

ENTRYPOINT ["nginx", "-g", "daemon off;"]

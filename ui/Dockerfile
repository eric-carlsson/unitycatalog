FROM node:lts-slim

COPY . /app
WORKDIR /app

RUN yarn

ENTRYPOINT ["yarn", "start"]

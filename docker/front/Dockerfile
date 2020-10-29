FROM node:12.16.1

WORKDIR /usr/src/app

COPY ./front/package.json .

COPY ./front/yarn.lock .

RUN yarn install

COPY . .

EXPOSE 3000

CMD yarn start

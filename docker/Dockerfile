FROM node:16.17.1-alpine

RUN apk update && apk add tini --no-cache

RUN mkdir -p /opt/app

ENV PATH="/opt/app/node_modules/.bin:${PATH}"

WORKDIR /opt/app

COPY ./package.json /opt/app
COPY ./package-lock.json /opt/app
COPY ./.npmrc /opt/app

RUN npm install -g @angular/cli
RUN npm install --no-progress && npm cache clean --force

EXPOSE 4200 49153

CMD [ "npm", "run", "start:dev" ]

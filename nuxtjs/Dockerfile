FROM node:14-alpine

RUN apk update

WORKDIR ${APP_ROOT}

COPY . ${APP_ROOT}

RUN npm ci

RUN npm run build

CMD [ "npm", "run", "start" ]

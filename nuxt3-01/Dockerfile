FROM node:17.3-alpine3.12 as development

WORKDIR /app

COPY ./package.json ./
COPY ./ ./

RUN yarn install

EXPOSE 3000

CMD [ "yarn", "dev" , "-o"]


FROM node:17.3-alpine3.12 as production

WORKDIR /app

COPY ./package.json ./
COPY ./ ./

RUN yarn build

RUN adduser -D user && chown -R user /app
USER user

EXPOSE 3000

CMD [ "yarn", "start" ]

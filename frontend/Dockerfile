FROM node:16 AS build

WORKDIR /usr/src/app

COPY . .

RUN npm install && \
npm run build

FROM node:16-alpine3.13

WORKDIR /usr/src/app

COPY --from=build /usr/src/app/build ./build

RUN npm install -g serve && \
    adduser -D appuser && \
    chown -R appuser /usr/src/app/build

USER appuser

EXPOSE 5000

CMD [ "serve", "-s", "build", "-l", "5000" ]

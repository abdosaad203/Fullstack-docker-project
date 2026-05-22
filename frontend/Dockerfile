FROM node:16-alpine AS build
WORKDIR /usr/src/app
COPY package*.json ./
RUN npm ci --legacy-peer-deps
COPY . .
RUN npm run build

FROM node:16-alpine
WORKDIR /usr/src/app
COPY --from=build /usr/src/app/build ./build
RUN apk add --no-cache wget && \
    npm install -g serve && \
    adduser -D appuser && \
    chown -R appuser /usr/src/app/build
USER appuser
EXPOSE 5000
HEALTHCHECK --interval=20s --timeout=5s --retries=3 \
    CMD wget -qO- http://localhost:5000 || exit 1
CMD [ "serve", "-s", "build", "-l", "5000" ]

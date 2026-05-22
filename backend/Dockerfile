FROM golang:1.23-alpine AS build
WORKDIR /usr/src/app
COPY go.mod go.sum ./
RUN go mod download
COPY . .
RUN CGO_ENABLED=0 go build -o server .

FROM alpine:3.20
WORKDIR /usr/src/app
RUN apk add --no-cache wget
COPY --from=build /usr/src/app/server .
RUN addgroup -S appgroup && adduser -S appuser -G appgroup
USER appuser
EXPOSE 8080
HEALTHCHECK --interval=20s --timeout=5s --retries=3 \
    CMD wget -qO- http://localhost:8080/ping || exit 1
ENTRYPOINT ["./server"]
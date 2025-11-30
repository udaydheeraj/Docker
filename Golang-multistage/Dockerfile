FROM golang:1.22 AS builder
WORKDIR /app
COPY go.mod .
COPY main.go .

RUN go build -o app

FROM alpine:latest
WORKDIR /app


COPY --from=builder /app/app  .



CMD  ["./app"]


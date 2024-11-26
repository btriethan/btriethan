# Build stage
FROM golang:1.21.13-alpine AS builder

WORKDIR /app

COPY . .

RUN go mod init golang-k8s-app
RUN go build -o main .

# Final stage
FROM alpine:latest

WORKDIR /app

COPY --from=builder /app/main .

EXPOSE 8080

CMD ["./main"]

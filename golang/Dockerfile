FROM golang:1.24.3-alpine AS builder

WORKDIR /app

COPY . .

RUN go mod download && go mod verify

RUN mkdir build && go build -o build/fizzbuzz

FROM gcr.io/distroless/base

COPY --from=builder /app/build/fizzbuzz .

COPY --from=builder /app/templates/index.html templates/

EXPOSE 8080

CMD ["build/fizzbuzz", "serve"]

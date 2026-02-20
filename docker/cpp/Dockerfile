FROM gcc:13 AS builder

WORKDIR /app
COPY . .
RUN g++ main.cpp -o app

FROM debian:stable-slim

WORKDIR /app
COPY --from=builder /app/app .

CMD ["./app"]

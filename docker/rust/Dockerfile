FROM rust:1.75-alpine AS builder

WORKDIR /app

COPY Cargo.toml Cargo.lock ./
RUN mkdir src && echo "fn main() {}" > src/main.rs
RUN cargo build --release

COPY . .
RUN cargo build --release

FROM alpine:3.19

WORKDIR /app

COPY --from=builder /app/target/release/app .

CMD ["./app"]

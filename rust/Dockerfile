FROM rust:1.80.1 as builder

WORKDIR /app

COPY . .

RUN cargo build --release
RUN strip /app/target/release/rust -o /app/target/release/rust

FROM gcr.io/distroless/cc-debian12:nonroot

USER nonroot

COPY --from=builder /app/target/release/rust /rust

CMD ["/rust"]

FROM golang:1.23.2 as builder

WORKDIR /app

COPY . .

RUN CGO_ENABLED=0 go build -o /app/bin/main

FROM scratch

COPY --from=builder /app/bin/main /main

CMD ["/main"]

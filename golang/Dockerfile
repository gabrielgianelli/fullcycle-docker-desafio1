FROM golang:1.17 AS builder

WORKDIR /go/src/app

COPY . .

RUN go mod init && \
    go build app.go

FROM scratch

COPY --from=builder /go/src/app .

CMD ["./app"]
FROM golang:alpine AS builder

WORKDIR /src

RUN go mod init example/hello

COPY hello.go .

RUN go build

FROM scratch

COPY --from=builder ./src/hello .

CMD ["./hello"]
FROM golang:1.21.3-alpine3.17 AS builder
WORKDIR /usr/src/app
COPY go.* ./
RUN go mod download
COPY . .
RUN go build -o .

FROM golang:1.21.3-alpine3.17 
WORKDIR /app
COPY --from=builder /usr/src/app .
ENTRYPOINT ["go","run","hello.go"]

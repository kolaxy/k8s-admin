#FROM golang:1.20
#
#WORKDIR /app
#
#COPY . .
#
#RUN go build -o main .
#
#CMD ["/app/main"]

FROM golang:1.20 as BUILD

WORKDIR /app

COPY . .

RUN go build -o main -o app

FROM alpine:latest

WORKDIR /app/

COPY --from=BUILD ./app .

CMD ["./app"]
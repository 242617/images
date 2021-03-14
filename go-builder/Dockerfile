FROM golang:1.16-alpine

RUN apk add --update \
    alpine-sdk \
    gettext \
    protobuf
RUN rm -rf /var/cache/apk

RUN go get github.com/golang/protobuf/protoc-gen-go

WORKDIR /root
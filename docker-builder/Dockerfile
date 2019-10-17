FROM docker:19.03.3-dind
MAINTAINER 242617@gmail.com

RUN apk add --update \
    alpine-sdk
RUN rm -rf /var/cache/apk

WORKDIR /root/image
RUN ls

CMD ls && make build && make save
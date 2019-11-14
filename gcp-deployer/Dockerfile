# Build jsonnet and jsonnetfmt
FROM alpine:latest AS builder

RUN apk -U add curl build-base

RUN mkdir /opt/jsonnet && \
    cd /opt/jsonnet && \
    curl -SL https://github.com/google/jsonnet/archive/v0.14.0.tar.gz \
    | tar -xz --strip-components=1 \
    && make

FROM google/cloud-sdk:alpine

RUN apk --no-cache add \
    gettext \
    jq \
    openssl \
    geth \
    nodejs \
    libstdc++
RUN gcloud components install kubectl

RUN curl -SL https://github.com/bitnami/kubecfg/releases/download/v0.12.5/kubecfg-linux-amd64 \
    -o /usr/local/bin/kubecfg && \
    chmod +x /usr/local/bin/kubecfg

COPY --from=builder /opt/jsonnet/jsonnet /usr/local/bin
COPY --from=builder /opt/jsonnet/jsonnetfmt /usr/local/bin
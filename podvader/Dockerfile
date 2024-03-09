FROM ghcr.io/hugomods/hugo:0.123.7 AS builder

ENV PODVADER_VERSION="0.0.1"

COPY . /src

RUN hugo --minify --gc

ARG BUILD_DATE
ARG REVISION
ARG VERSION

FROM nginx:1.25.4-alpine-slim@sha256:3d819042aa3b1f8eef5f1d923d3f34c287e43dc7e6b4dac3bbdfe018265932c8

LABEL org.opencontainers.image.created=${BUILD_DATE}
LABEL org.opencontainers.image.authors="https://nahue.ar"
LABEL org.opencontainers.image.url="https://github.com/NPastorale/containers/rsync"
LABEL org.opencontainers.image.documentation="https://github.com/NPastorale/containers/podvader"
LABEL org.opencontainers.image.source="https://github.com/NPastorale/containers"
LABEL org.opencontainers.image.version=${VERSION}
LABEL org.opencontainers.image.revision=${REVISION}
LABEL org.opencontainers.image.licenses="MIT"
LABEL org.opencontainers.image.title="podvader"
LABEL org.opencontainers.image.description="A home for technical knowledge and rants."

COPY --from=builder /src/public /usr/share/nginx/html
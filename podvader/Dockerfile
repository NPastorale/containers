FROM ghcr.io/hugomods/hugo:0.160.1@sha256:cb4106ffd926692b2d0c62f768601f9323faddd4e4ee05d9d58ee0e08de77055 AS builder

ENV PODVADER_VERSION="0.0.1"

COPY /podvader /src

RUN hugo --minify --gc

ARG BUILD_DATE
ARG REVISION
ARG VERSION

FROM nginx:1.30.0-alpine-slim@sha256:830b40ff1beb5e018e56aef2ed1f9fe87a7797e35a555b75fea5c9568e316b04

LABEL org.opencontainers.image.created=${BUILD_DATE}
LABEL org.opencontainers.image.authors="https://nahue.ar"
LABEL org.opencontainers.image.url="https://github.com/NPastorale/containers/podvader"
LABEL org.opencontainers.image.documentation="https://github.com/NPastorale/containers/podvader"
LABEL org.opencontainers.image.source="https://github.com/NPastorale/containers"
LABEL org.opencontainers.image.version=${VERSION}
LABEL org.opencontainers.image.revision=${REVISION}
LABEL org.opencontainers.image.licenses="MIT"
LABEL org.opencontainers.image.title="podvader"
LABEL org.opencontainers.image.description="A home for technical knowledge and rants."

COPY --from=builder /src/public /usr/share/nginx/html
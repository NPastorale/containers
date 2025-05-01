FROM ghcr.io/hugomods/hugo:0.147.1@sha256:d8dae8479fcc0b5f1fbe904bdf29a776022c62158128184246113a259c9722bb AS builder

ENV PODVADER_VERSION="0.0.1"

COPY /podvader /src

RUN hugo --minify --gc

ARG BUILD_DATE
ARG REVISION
ARG VERSION

FROM nginx:1.28.0-alpine-slim@sha256:39a9a15e0a81914a96fa9ffa980cdfe08e2e5e73ae3424f341ad1f470147c413

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
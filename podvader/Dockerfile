FROM ghcr.io/hugomods/hugo:0.124.1@sha256:e58c5c3a536cdf8433007c8776e2c8b6a29c085e735510626934f821999c5a47 AS builder

ENV PODVADER_VERSION="0.0.1"

COPY /podvader /src

RUN hugo --minify --gc

ARG BUILD_DATE
ARG REVISION
ARG VERSION

FROM nginx:1.25.4-alpine-slim@sha256:b841779b72c127bdcb6e58b2ae3d810f890e020460858d84c7bd38d15cf26ddf

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
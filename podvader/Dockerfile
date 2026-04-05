FROM ghcr.io/hugomods/hugo:0.160.0@sha256:2aa05cf9ea5049b577e57af598adee7f7ddd84d394581a63941f979499e58256 AS builder

ENV PODVADER_VERSION="0.0.1"

COPY /podvader /src

RUN hugo --minify --gc

ARG BUILD_DATE
ARG REVISION
ARG VERSION

FROM nginx:1.29.7-alpine-slim@sha256:0848ca84c476868cbeb6a5c2c009a98821b8540f96c44b1ba06820db50262e35

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
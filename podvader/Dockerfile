FROM ghcr.io/hugomods/hugo:0.125.3@sha256:5b7a9a5f609b1867f5f3fa4692f4ee9703cb6887d8545246b14e7811a6760956 AS builder

ENV PODVADER_VERSION="0.0.1"

COPY /podvader /src

RUN hugo --minify --gc

ARG BUILD_DATE
ARG REVISION
ARG VERSION

FROM nginx:1.25.5-alpine-slim@sha256:b27fd01b23890c5f807a00f48b7d636929356f50c1432579ae291752e49465f4

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
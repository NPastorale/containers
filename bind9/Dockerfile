FROM alpine:3.21.2@sha256:56fa17d2a7e7f168a043a2712e63aed1f8543aeafdcee47c58dcffe38ed51099

# renovate: datasource=repology depName=alpine_3_21/bind versioning=loose
ENV BIND_VERSION="9.18.33-r0"
# renovate: datasource=repology depName=alpine_3_21/tzdata versioning=loose
ENV TZDATA_VERSION="2024b-r1"

ARG BUILD_DATE
ARG REVISION
ARG VERSION

LABEL org.opencontainers.image.created=${BUILD_DATE}
LABEL org.opencontainers.image.authors="https://nahue.ar"
LABEL org.opencontainers.image.url="https://github.com/NPastorale/containers/bind9"
LABEL org.opencontainers.image.documentation="https://github.com/NPastorale/containers/bind9"
LABEL org.opencontainers.image.source="https://github.com/NPastorale/containers"
LABEL org.opencontainers.image.version=${VERSION}
LABEL org.opencontainers.image.revision=${REVISION}
LABEL org.opencontainers.image.licenses="MIT"
LABEL org.opencontainers.image.title="Bind 9"
LABEL org.opencontainers.image.description="Bind 9 DNS server running on Alpine Linux, providing DNS resolution services."

RUN apk update && \
    apk --no-cache add \
    bind="${BIND_VERSION}" \
    tzdata="${TZDATA_VERSION}"

CMD [ "named", "-f" ]

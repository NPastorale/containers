FROM alpine:3.24.3@sha256:b3413572228e34bd1c9245f5565e6cd127005655e8a7899aef33d8e83255c9e6

# renovate: datasource=repology depName=alpine_3_24/bind versioning=loose
ENV BIND_VERSION="9.20.30-r0"
# renovate: datasource=repology depName=alpine_3_24/tzdata versioning=loose
ENV TZDATA_VERSION="2026e-r0"

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

FROM alpine:3.20.1@sha256:ff5265e55d2f71d89d17ee63a634e37686637d2e2c8e76e57837e010c8666904

# renovate: datasource=repology depName=alpine_3_20/bind versioning=loose
ENV BIND_VERSION="9.18.27-r0"
# renovate: datasource=repology depName=alpine_3_20/tzdata versioning=loose
ENV TZDATA_VERSION="2024a-r1"

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

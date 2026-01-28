FROM alpine:3.23.3@sha256:25109184c71bdad752c8312a8623239686a9a2071e8825f20acb8f2198c3f659

# renovate: datasource=repology depName=alpine_3_23/bind versioning=loose
ENV BIND_VERSION="9.20.18-r0"
# renovate: datasource=repology depName=alpine_3_23/tzdata versioning=loose
ENV TZDATA_VERSION="2025c-r0"

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

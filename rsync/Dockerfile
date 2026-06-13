FROM alpine:3.24.0@sha256:a2d49ea686c2adfe3c992e47dc3b5e7fa6e6b5055609400dc2acaeb241c829f4

# renovate: datasource=repology depName=alpine_3_23/bash versioning=loose
ENV BASH_VERSION="5.3.9-r1"
# renovate: datasource=repology depName=alpine_3_23/curl versioning=loose
ENV CURL_VERSION="8.20.0-r1 "
# renovate: datasource=repology depName=alpine_3_23/rsync versioning=loose
ENV RSYNC_VERSION="3.4.3-r1"
# renovate: datasource=repology depName=alpine_3_23/tzdata versioning=loose
ENV TZDATA_VERSION="2026b-r0"

ARG BUILD_DATE
ARG REVISION
ARG VERSION

LABEL org.opencontainers.image.created=${BUILD_DATE}
LABEL org.opencontainers.image.authors="https://nahue.ar"
LABEL org.opencontainers.image.url="https://github.com/NPastorale/containers/rsync"
LABEL org.opencontainers.image.documentation="https://github.com/NPastorale/containers/rsync"
LABEL org.opencontainers.image.source="https://github.com/NPastorale/containers"
LABEL org.opencontainers.image.version=${VERSION}
LABEL org.opencontainers.image.revision=${REVISION}
LABEL org.opencontainers.image.licenses="MIT"
LABEL org.opencontainers.image.title="rsync"
LABEL org.opencontainers.image.description="rsync: a fast and versatile file synchronization tool, allowing efficient copying, mirroring, and backup of files between systems over a network or locally."

RUN apk update && \
    apk --no-cache add \
    bash="${BASH_VERSION}" \
    curl="${CURL_VERSION}" \
    rsync="${RSYNC_VERSION}" \
    tzdata="${TZDATA_VERSION}"

ENTRYPOINT [ "rsync" ]

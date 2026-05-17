FROM alpine:3.23.4@sha256:5b10f432ef3da1b8d4c7eb6c487f2f5a8f096bc91145e68878dd4a5019afde11

# renovate: datasource=repology depName=alpine_3_23/bash versioning=loose
ENV BASH_VERSION="5.3.3-r1"
# renovate: datasource=repology depName=alpine_3_23/curl versioning=loose
ENV CURL_VERSION="8.19.0-r0"
# renovate: datasource=repology depName=alpine_3_23/rsync versioning=loose
ENV RSYNC_VERSION="3.4.2-r0"
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

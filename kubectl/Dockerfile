FROM alpine:3.23.2@sha256:865b95f46d98cf867a156fe4a135ad3fe50d2056aa3f25ed31662dff6da4eb62

# renovate: datasource=repology depName=alpine_3_23/bash versioning=loose
ENV BASH_VERSION="5.3.3-r1"
# renovate: datasource=repology depName=alpine_3_23/curl versioning=loose
ENV CURL_VERSION="8.17.0-r1"
# renovate: datasource=repology depName=alpine_3_23/iputils-ping versioning=loose
ENV IPUTILS_PING_VERSION="20250605-r0"
# renovate: datasource=repology depName=alpine_3_23/kubernetes versioning=loose
ENV KUBECTL_VERSION="1.34.2-r2"

ARG BUILD_DATE
ARG REVISION
ARG VERSION

LABEL org.opencontainers.image.created=${BUILD_DATE}
LABEL org.opencontainers.image.authors="https://nahue.ar"
LABEL org.opencontainers.image.url="https://github.com/NPastorale/containers/kubectl"
LABEL org.opencontainers.image.documentation="https://github.com/NPastorale/containers/kubectl"
LABEL org.opencontainers.image.source="https://github.com/NPastorale/containers"
LABEL org.opencontainers.image.version=${VERSION}
LABEL org.opencontainers.image.revision=${REVISION}
LABEL org.opencontainers.image.licenses="MIT"
LABEL org.opencontainers.image.title="kubectl"
LABEL org.opencontainers.image.description="kubectl: Kubernetes Command-Line Tool, allowing interaction with Kubernetes clusters for deployment, management, and monitoring of containerized applications."

RUN apk update && \
    apk --no-cache add \
    bash="${BASH_VERSION}" \
    curl="${CURL_VERSION}" \
    iputils-ping="${IPUTILS_PING_VERSION}" \
    kubectl="${KUBECTL_VERSION}"

CMD [ "kubectl" ]

FROM alpine:3.24.2@sha256:31b6477333eb8257db9e5d7c3a7264fd0467928756f0bbcc27d35bea5d28cdbd

# renovate: datasource=repology depName=alpine_3_24/bash versioning=loose
ENV BASH_VERSION="5.3.9-r1"
# renovate: datasource=repology depName=alpine_3_24/curl versioning=loose
ENV CURL_VERSION="8.22.0-r0"
# renovate: datasource=repology depName=alpine_3_24/iputils-ping versioning=loose
ENV IPUTILS_PING_VERSION="20250605-r2"
# renovate: datasource=repology depName=alpine_3_24/kubernetes versioning=loose
ENV KUBECTL_VERSION="1.36.1-r1"

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

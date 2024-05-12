FROM alpine:3.19.1@sha256:c5b1261d6d3e43071626931fc004f70149baeba2c8ec672bd4f27761f8e1ad6b

# renovate: datasource=repology depName=alpine_3_19/bash versioning=loose
ENV BASH_VERSION="5.2.21-r0"
# renovate: datasource=repology depName=alpine_3_19/curl versioning=loose
ENV CURL_VERSION="8.5.0-r0"
# renovate: datasource=repology depName=alpine_3_19/iputils-ping versioning=loose
ENV IPUTILS_PING_VERSION="20221126-r2"
# renovate: datasource=repology depName=alpine_3_19/kubectl versioning=loose
ENV KUBECTL_VERSION="1.28.4-r3"

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
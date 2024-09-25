FROM alpine:3.20.3@sha256:a8f120106f5549715aa966fd7cefaf3b7045f6414fed428684de62fec8c2ca4b

# renovate: datasource=repology depName=alpine_3_20/bash versioning=loose
ENV BASH_VERSION="5.2.26-r0"
# renovate: datasource=repology depName=alpine_3_20/curl versioning=loose
ENV CURL_VERSION="8.10.0-r0"
# renovate: datasource=repology depName=alpine_3_20/iputils-ping versioning=loose
ENV IPUTILS_PING_VERSION="20240117-r0"
# renovate: datasource=repology depName=alpine_3_20/kubectl versioning=loose
ENV KUBECTL_VERSION="1.30.0-r3"

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
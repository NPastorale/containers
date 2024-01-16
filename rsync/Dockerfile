FROM alpine:3.19.0

LABEL org.opencontainers.image.authors="https://nahue.ar"
LABEL org.opencontainers.image.source="https://github.com/NPastorale/containers"

RUN apk update && \
    apk --no-cache add \
    rsync \
    bash \
    curl \
    tzdata

ENTRYPOINT [ "rsync" ]
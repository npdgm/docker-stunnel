FROM alpine:3.12
ARG VERSION
LABEL maintainer="Thibault VINCENT <root@paraneko.org>" \
    org.opencontainers.image.title="Stunnel on Alpine 3.12" \
    org.opencontainers.image.description="Alpine Linux 3.12 with Stunnel installed from distro repositories." \
    org.opencontainers.image.url="https://hub.docker.com/r/npdgm/stunnel" \
    org.opencontainers.image.documentation="https://hub.docker.com/r/npdgm/stunnel" \
    org.opencontainers.image.authors="Thibault VINCENT <root@paraneko.org>" \
    org.opencontainers.image.licenses="Apache-2.0" \
    org.opencontainers.image.version="$VERSION"
RUN apk add --no-cache stunnel
VOLUME /etc/stunnel
WORKDIR /var/lib/stunnel
ENTRYPOINT /usr/bin/stunnel

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

ENTRYPOINT ["/usr/bin/stunnel"]

RUN apk add --no-cache stunnel \
 && chown stunnel:stunnel /var/lib/stunnel \
 && chmod 0755 /var/lib/stunnel

USER stunnel:stunnel
WORKDIR /var/lib/stunnel
VOLUME /etc/stunnel

ARG VCS_REF
ARG BUILD_DATE
LABEL org.opencontainers.image.revision="$VCS_REF" \
      org.opencontainers.image.created="$BUILD_DATE"

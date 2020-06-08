FROM debian:10

ARG VERSION
LABEL maintainer="Thibault VINCENT <root@paraneko.org>" \
      org.opencontainers.image.title="Stunnel on Debian 10" \
      org.opencontainers.image.description="Debian 10 (buster) with Stunnel installed from distro repositories." \
      org.opencontainers.image.url="https://hub.docker.com/r/npdgm/stunnel" \
      org.opencontainers.image.documentation="https://hub.docker.com/r/npdgm/stunnel" \
      org.opencontainers.image.authors="Thibault VINCENT <root@paraneko.org>" \
      org.opencontainers.image.licenses="Apache-2.0" \
      org.opencontainers.image.version="$VERSION"

ENTRYPOINT ["/usr/bin/stunnel4"]

RUN apt-get update \
 && apt-get install -y --no-install-recommends stunnel4

USER stunnel4:stunnel4
WORKDIR /var/lib/stunnel4
VOLUME /etc/stunnel

ARG VCS_REF
ARG BUILD_DATE
LABEL org.opencontainers.image.revision="$VCS_REF" \
      org.opencontainers.image.created="$BUILD_DATE"

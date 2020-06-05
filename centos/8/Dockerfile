FROM centos:centos8
ARG VERSION
LABEL maintainer="Thibault VINCENT <root@paraneko.org>" \
    org.opencontainers.image.title="Stunnel on CentOS 8" \
    org.opencontainers.image.description="CentOS 8 with Stunnel installed from distro repositories." \
    org.opencontainers.image.url="https://hub.docker.com/r/npdgm/stunnel" \
    org.opencontainers.image.documentation="https://hub.docker.com/r/npdgm/stunnel" \
    org.opencontainers.image.authors="Thibault VINCENT <root@paraneko.org>" \
    org.opencontainers.image.licenses="Apache-2.0" \
    org.opencontainers.image.version="$VERSION"
RUN yum -y install stunnel \
 && yum clean all \
 && useradd -r -U -M -u 110 -d /var/lib/stunnel -s /bin/sh stunnel \
 && mkdir /var/lib/stunnel \
 && chown stunnel:stunnel /var/lib/stunnel
VOLUME /etc/stunnel
WORKDIR /var/lib/stunnel
USER stunnel:stunnel
ENTRYPOINT ["/usr/bin/stunnel"]

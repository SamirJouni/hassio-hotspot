ARG BUILD_FROM
FROM $BUILD_FROM

MAINTAINER Samir Jouni <git@samirjouni.com>

SHELL ["/bin/bash", "-o", "pipefail", "-c"]

ENV LANG C.UTF-8

RUN apk update && \
apk add --no-cache bash jq iw hostapd networkmanager net-tools sudo dnsmasq && \
rm -rf /var/cache/apk/*

COPY hostapd.conf /
COPY dnsmasq.conf /

COPY rootfs/etc/services.d/hassio-hotspot/run.sh /
RUN chmod a+x /run.sh

CMD [ "/run.sh" ]

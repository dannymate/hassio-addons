FROM ghcr.io/hassio-addons/ubuntu-base:8.1.1 as build
SHELL ["/bin/bash", "-o", "pipefail", "-c"]
# hadolint ignore=SC2181, DL3008
RUN \
    apt-get update \
    && apt-get install -y --no-install-recommends \
	openrc \
	curl 
    
    #&& curl -L -o /tmp/netbird_0.9.7.tar.gz https://github.com/netbirdio/netbird/releases/download/v0.9.7/netbird_0.9.7_linux_amd64.tar.gz  \
    #&& tar -xvf /tmp/netbird_0.9.7.tar.gz \
    #&& chmod +x /tmp/netbird

ARG BUILD_FROM=gcr.io/distroless/base:debug
# hadolint ignore=DL3006
FROM ${BUILD_FROM}

ENV NB_LOG_FILE=console

# Set shell
SHELL ["/busybox/sh","-c"]
RUN sed -i -E 's/(^root:.+)\/sbin\/nologin/\1\/busybox\/sh/g' /etc/passwd
# Setup base system
#ARG BUILD_ARCH=amd64
# hadolint ignore=SC2181, DL3008
#RUN \
#    apt-get update \
#    && apt-get install -y --no-install-recommends \
#	openrc \
#	curl \
#    \
#    && curl -L -o /tmp/netbird_0.9.7.tar.gz https://github.com/netbirdio/netbird/releases/download/v0.9.7/netbird_0.9.7_linux_amd64.tar.gz  \
#    && cd /tmp/ \
#    && tar -xvf /tmp/netbird_0.9.7.tar.gz \
#    && mv netbird /go/bin/netbird \
#    && chmod +x /go/bin/netbird \
#    && export PATH=$PATH:/go/bin \
#    \
#    && rm -f -r \
#        /tmp/*

# Copy root filesystem
COPY rootfs /
COPY --from=build /tmp/netbird /go/bin/netbird

# Build arguments
ARG BUILD_ARCH
ARG BUILD_DATE
ARG BUILD_DESCRIPTION
ARG BUILD_NAME
ARG BUILD_REF
ARG BUILD_REPOSITORY
ARG BUILD_VERSION

# Labels
LABEL \
    io.hass.name="${BUILD_NAME}" \
    io.hass.description="${BUILD_DESCRIPTION}" \
    io.hass.arch="${BUILD_ARCH}" \
    io.hass.type="addon" \
    io.hass.version=${BUILD_VERSION} \
    maintainer="Franck Nijhof <frenck@addons.community>" \
    org.opencontainers.image.title="${BUILD_NAME}" \
    org.opencontainers.image.description="${BUILD_DESCRIPTION}" \
    org.opencontainers.image.vendor="Home Assistant Community Add-ons" \
    org.opencontainers.image.authors="Franck Nijhof <frenck@addons.community>" \
    org.opencontainers.image.licenses="MIT" \
    org.opencontainers.image.url="https://addons.community" \
    org.opencontainers.image.source="https://github.com/${BUILD_REPOSITORY}" \
    org.opencontainers.image.documentation="https://github.com/${BUILD_REPOSITORY}/blob/main/README.md" \
    org.opencontainers.image.created=${BUILD_DATE} \
    org.opencontainers.image.revision=${BUILD_REF} \
    org.opencontainers.image.version=${BUILD_VERSION}

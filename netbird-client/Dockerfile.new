FROM gcr.io/distroless/base:debug
ENV WT_LOG_FILE=console
ENV PATH=/sbin:/usr/sbin:/bin:/usr/bin:/busybox
SHELL ["/busybox/sh","-c"]
RUN sed -i -E 's/(^root:.+)\/sbin\/nologin/\1\/busybox\/sh/g' /etc/passwd
RUN \
    apt-get update \
    && apt-get install -y --no-install-recommends \
	openrc \
	curl \
    \
    && curl -L -o /tmp/netbird_0.9.7.tar.gz https://github.com/netbirdio/netbird/releases/download/v0.9.7/netbird_0.9.7_linux_amd64.tar.gz  \
    && cd /tmp/ \
    && tar -xvf /tmp/netbird_0.9.7.tar.gz \
    && mv netbird /go/bin/netbird \
    && chmod +x /go/bin/netbird \
    && export PATH=$PATH:/go/bin \
    \
    && rm -f -r \
        /tmp/*

ENTRYPOINT [ "/go/bin/netbird","up"]
COPY rootfs /

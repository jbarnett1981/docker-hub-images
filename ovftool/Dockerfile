FROM ubuntu:latest

MAINTAINER Julian Barnett <digitalsy@gmail.com>

RUN apt-get update && \
    apt-get install -y curl gzip jq git python3 python3-pip && \
    pip3 install lxml

# Install ovftool
ENV OVFTOOL_FILENAME=VMware-ovftool-4.3.0-13981069-lin.x86_64.bundle
ADD $OVFTOOL_FILENAME /tmp/
WORKDIR /root
RUN /bin/sh /tmp/$OVFTOOL_FILENAME --console --required --eulas-agreed && \
    rm -f /tmp/$OVFTOOL_FILENAME

ENTRYPOINT ["ovftool"]

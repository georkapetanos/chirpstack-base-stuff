# syntax=docker/dockerfile:1

FROM --platform=linux/arm64 ubuntu:focal

RUN apt-get update && apt-get -y install --no-install-recommends \
    nano

COPY ./chirpstack-gateway-bridge_3.14.2_linux_arm64.deb /tmp/chirpstack-gateway-bridge_3.14.2_linux_arm64.deb

RUN dpkg -i /tmp/chirpstack-gateway-bridge_3.14.2_linux_arm64.deb
RUN rm /tmp/chirpstack-gateway-bridge_3.14.2_linux_arm64.deb

COPY ./configuration/chirpstack-gateway-bridge.toml /etc/chirpstack-gateway-bridge/chirpstack-gateway-bridge.toml

RUN mkdir -p /tmp/zeromq

ENTRYPOINT ["/usr/bin/chirpstack-gateway-bridge","-c","/etc/chirpstack-gateway-bridge/chirpstack-gateway-bridge.toml"]

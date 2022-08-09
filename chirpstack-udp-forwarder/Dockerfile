# syntax=docker/dockerfile:1

FROM --platform=linux/arm64 ubuntu:focal

RUN apt-get update && apt-get -y install --no-install-recommends \
    nano

COPY ./bin/chirpstack-udp-forwarder /usr/bin/chirpstack-udp-forwarder

COPY ./configuration/chirpstack-udp-forwarder.toml /etc/chirpstack-udp-forwarder/chirpstack-udp-forwarder.toml

RUN mkdir -p /tmp/zeromq

ENTRYPOINT ["/usr/bin/chirpstack-udp-forwarder","-c/etc/chirpstack-udp-forwarder/chirpstack-udp-forwarder.toml"]

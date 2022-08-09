# syntax=docker/dockerfile:1

FROM --platform=linux/arm64 ubuntu:focal

RUN apt-get update && apt-get -y install --no-install-recommends \
    nano

RUN mkdir -p /etc/chirpstack-concentratord/sx1302
RUN mkdir -p /tmp/zeromq

COPY ./configuration/channels.toml /etc/chirpstack-concentratord/sx1302/channels.toml
COPY ./configuration/global.toml /etc/chirpstack-concentratord/sx1302/global.toml
COPY ./configuration/beacon.toml /etc/chirpstack-concentratord/sx1302/beacon.toml

COPY ./bin/chirpstack-concentratord-sx1302 /usr/bin/chirpstack-concentratord-sx1302
COPY ./bin/gateway-id /usr/bin/gateway-id
COPY ./bin/concentrator-exec /usr/bin/concentrator-exec

ENTRYPOINT ["concentrator-exec"]
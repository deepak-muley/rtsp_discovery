#
# Dockerfile for nmap + rtsp stream discovery scripts
#

FROM instrumentisto/nmap:7.70
MAINTAINER Deepak <deepak.muley@gmail.com>

RUN apk add --update --no-cache --virtual .build-deps \
        wget \
 && apk del .build-deps \
 && rm -rf /var/cache/apk/* 

WORKDIR /data

RUN wget https://svn.nmap.org/nmap/scripts/rtsp-url-brute.nse

FROM alpine

WORKDIR /

USER root

RUN echo "http://dl-2.alpinelinux.org/alpine/edge/main" > /etc/apk/repositories
RUN echo "http://dl-2.alpinelinux.org/alpine/edge/community" >> /etc/apk/repositories
RUN echo "http://dl-2.alpinelinux.org/alpine/edge/testing" >> /etc/apk/repositories

ENV CHROME_BIN=/usr/bin/chromium-browser
ENV CHROME_PATH=/usr/lib/chromium/

#-----------------
# Add packages
#-----------------

RUN apk -U --no-cache update
RUN apk -U --no-cache add \
    chromium

# Minimize size
RUN apk del --purge --force curl make gcc g++ python linux-headers binutils-gold gnupg git zlib-dev apk-tools libc-utils

FROM node:alpine

WORKDIR /

USER root

RUN echo "http://dl-2.alpinelinux.org/alpine/edge/main" > /etc/apk/repositories
RUN echo "http://dl-2.alpinelinux.org/alpine/edge/community" >> /etc/apk/repositories
RUN echo "http://dl-2.alpinelinux.org/alpine/edge/testing" >> /etc/apk/repositories
RUN apk -U --no-cache update
# Minimize size
RUN apk del --purge --force curl make gcc g++ python linux-headers binutils-gold gnupg git zlib-dev apk-tools libc-utils

RUN rm -rf /var/lib/apt/lists/* \
    /var/cache/apk/* \
    /usr/share/man \
    /tmp/* \
    /usr/lib/node_modules/npm/man \
    /usr/lib/node_modules/npm/doc \
    /usr/lib/node_modules/npm/html \
    /usr/lib/node_modules/npm/scripts

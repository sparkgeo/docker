FROM smebberson/alpine-nginx:latest
MAINTAINER Michael Connor <mike@sparkgeo.com>

RUN ln -sf /dev/stdout /var/log/nginx/access.log && \
    ln -sf /dev/stderr /var/log/nginx/error.log

RUN apk update && apk upgrade

# install ca-certificates so that HTTPS works consistently
# the other runtime dependencies for Python are installed later
RUN apk add --no-cache ca-certificates

# Install Python
RUN apk add --update \
    python \
    python-dev \
    py-pip \
    build-base \
  && rm -rf /var/cache/apk/*

RUN pip install gunicorn

# Ports 80, 443 are already exposed.

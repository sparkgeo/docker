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

# Install and configure Gunicorn
RUN pip install gunicorn
RUN mkdir -p -m 777 /var/log/gunicorn/
# To add your app to S6, add a run file to /etc/services.d/gunicorn/run.
# See here for example: https://github.com/just-containers/s6-overlay#writing-a-service-script
# example for Gunicorn command: gunicorn main.wsgi:application -c /mermaid_api/gunicorn.conf

# Ports 80, 443 are already exposed.

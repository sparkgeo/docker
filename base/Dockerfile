###############################################################################
# Environment
###############################################################################

FROM debian:jessie
MAINTAINER <hi@sparkgeo.com>

ENV DEBIAN_FRONTEND noninteractive
ENV LANG C.UTF-8
ENV LANGUAGE C.UTF-8
ENV LC_ALL C.UTF-8

###############################################################################
# Libraries
###############################################################################

# Pre apt-get install
RUN apt-get update && apt-get install -y curl
RUN curl -sL https://deb.nodesource.com/setup_6.x | bash -

# Post apt-get install
RUN apt-get update && apt-get install -y --no-install-recommends \
    build-essential \
    git \
    libffi-dev \
    libmemcached-dev \
    libpq-dev \
    libxslt-dev \
    nginx \
    nodejs \
    postgis \
    postgresql \
    python-dev \
    python-pip \
    ruby \
    supervisor \
    vim \
    gunicorn

RUN pip install --upgrade pip

RUN gem install sass ultrahook

RUN npm install -g bower gulp jspm

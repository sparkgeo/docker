FROM ubuntu:16.04

RUN apt-get update && apt-get install -y \
    build-essential \
    git \
    libboost-all-dev \
    libicu-dev \
    libz-dev \
    libfreetype6-dev \
    libxml2-dev \
    libharfbuzz-dev \
    libpng12-dev \
    libjpeg-dev \
    libtiff-dev \
    libwebp-dev \
    libproj-dev \
    libcairo2-dev \
    libpq-dev \
    libgdal-dev \
    vim \
    python3 \
    python3-setuptools \
    python3-pip

RUN mkdir -p /build
WORKDIR /build

# Mapnik
RUN git clone https://github.com/mapnik/mapnik.git
WORKDIR /build/mapnik
RUN git submodule update --init
RUN ./configure && make && make install

# Python-Mapnik
WORKDIR /build/
RUN git clone https://github.com/mapnik/python-mapnik.git
WORKDIR /build/python-mapnik
RUN python3 setup.py install

# Clean up
RUN rm -R /build

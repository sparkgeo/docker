FROM circleci/node:8

MAINTAINER Sparkgeo

# Install awscli
RUN sudo apt-get update
RUN sudo apt-get install python-pip python-dev jq
RUN sudo pip install awscli

# Install docker-compose
RUN curl -L https://github.com/docker/compose/releases/download/1.19.0/docker-compose-`uname -s`-`uname -m` > ~/docker-compose
RUN chmod +x ~/docker-compose
RUN sudo mv ~/docker-compose /usr/local/bin/docker-compose

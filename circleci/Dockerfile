FROM circleci/node:8

MAINTAINER Sparkgeo

# Install awscli and boto3
RUN sudo apt-get update
RUN sudo apt-get install python-pip python-dev jq libgeos-dev
RUN sudo pip install awscli boto3
RUN sudo pip install setuptools --upgrade

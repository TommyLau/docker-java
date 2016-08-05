FROM ubuntu:16.04

MAINTAINER Tommy Lau <tommy@gen-new.com>

# Default to UTF-8 file.encoding
ENV LANG C.UTF-8

# Install Oracle JDK 1.8
RUN apt-get update -qq \
    && apt-get install -y --no-install-recommends curl libtcnative-1 software-properties-common \
    && echo oracle-java8-installer shared/accepted-oracle-license-v1-1 select true | debconf-set-selections \
    && apt-add-repository -y ppa:webupd8team/java \
    && apt-get update -qq \
    && apt-get install -y --no-install-recommends oracle-java8-installer \
    && apt-get clean autoclean \
    && apt-get autoremove --yes \
    && rm -rf /var/lib/{apt,dpkg,cache,log}/

ENV JAVA_HOME /usr/lib/jvm/java-8-oracle

ENV LD_LIBRARY_PATH /usr/lib/x86_64-linux-gnu:/usr/java/packages/lib/amd64:/usr/lib64:/lib64:/lib:/usr/lib


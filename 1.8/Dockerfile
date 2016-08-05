FROM ubuntu:16.04

MAINTAINER Tommy Lau <tommy@gen-new.com>

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

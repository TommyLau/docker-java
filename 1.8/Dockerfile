FROM debian:jessie

MAINTAINER Tommy Lau <tommy@gen-new.com>

# Default to UTF-8 file.encoding
ENV LANG C.UTF-8

# Install Oracle JDK 1.8
RUN echo "deb http://ppa.launchpad.net/webupd8team/java/ubuntu xenial main" | tee /etc/apt/sources.list.d/webupd8team-java.list \
    && echo "deb-src http://ppa.launchpad.net/webupd8team/java/ubuntu xenial main" | tee -a /etc/apt/sources.list.d/webupd8team-java.list \
    && apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys EEA14886 \
    && apt-get update -qq \
    && echo oracle-java8-installer shared/accepted-oracle-license-v1-1 select true | debconf-set-selections \
    && apt-get install -y --no-install-recommends ca-certificates curl libtcnative-1 oracle-java8-installer \
    && apt-get clean autoclean \
    && apt-get autoremove --yes \
    && rm -rf /var/lib/{apt,dpkg,cache,log}/ \
    && ln -s  /usr/lib/x86_64-linux-gnu/libtcnative-1.so /usr/lib/libtcnative-1.so

ENV JAVA_HOME /usr/lib/jvm/java-8-oracle


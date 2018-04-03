# Image: glassfish
# Author: ademord
# Description: Containerized Application for the IT_Security lectures.
# Copyright © 2017-2019 Zuercher Hochschule fuer Angewandte Wissenschaften.

FROM        openjdk:8-jdk

MAINTAINER  Almir Dzinovic <almirdzin@gmail.com>

ENV         JAVA_HOME         /usr/lib/jvm/java-8-openjdk-amd64
ENV         GLASSFISH_HOME    /usr/glassfish
ENV         PATH              $PATH:$JAVA_HOME/bin:$GLASSFISH_HOME/bin

RUN         apt-get update && \
            apt-get install -y curl unzip zip inotify-tools && \
            rm -rf /var/lib/apt/lists/*

RUN         curl -L -o /tmp/glassfish5.zip http://download.oracle.com/glassfish/5.0/release/glassfish-5.0.zip && \
            unzip /tmp/glassfish5.zip -d /usr && \
            mv -f /usr/glassfish5 /usr/glassfish && \
            rm -f /tmp/glassfish5.zip && \
            find /usr/glassfish/glassfish/ -name "*.bat" -exec rm -f {} \;

EXPOSE      8080 4848 8181

WORKDIR     /usr/glassfish

# verbose causes the process to remain in the foreground so that docker can track it
CMD         asadmin start-domain enable-secure-admin --verbose
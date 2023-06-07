# syntax=docker/dockerfile:1

FROM jenkins/jenkins:lts

LABEL maintainer="Tuan Anh Nguyen <nguyenhuutuananh2@gmail.com>"

# https://www.jenkins.io/doc/book/installing/docker/#downloading-and-running-jenkins-in-docker

USER root

RUN apt-get update && apt-get install -y lsb-release

RUN curl -fsSLo /usr/share/keyrings/docker-archive-keyring.asc \
  https://download.docker.com/linux/debian/gpg

RUN echo "deb [arch=$(dpkg --print-architecture) \
  signed-by=/usr/share/keyrings/docker-archive-keyring.asc] \
  https://download.docker.com/linux/debian \
  $(lsb_release -cs) stable" > /etc/apt/sources.list.d/docker.list

# Clean up
RUN apt-get clean && \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* && \
    rm /var/log/lastlog /var/log/faillog

EXPOSE 8080

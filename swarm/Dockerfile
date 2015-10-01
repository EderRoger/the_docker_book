FROM ubuntu:14.04
MAINTAINER Eder Roger <eder.roger.souza@gmail.com>
ENV REFRESHED_AT 2014-06-01
RUN apt-get update -y && apt-get install -y curl apt-transport-https
RUN curl https://get.docker.com/gpg | apt-key add -
RUN echo deb http://get.docker.com/ubuntu docker main > /etc/apt/sources.list.d/docker.list
RUN apt-get update -y && apt-get install -y iptables ca-certificates lxc lxc-docker

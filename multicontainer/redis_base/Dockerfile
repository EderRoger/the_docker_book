FROM ubuntu:14.04
MAINTAINER Eder Roger <eder.roger.souza@gmail.com>
ENV REFRESHED_AT 2014-06-01

RUN apt-get -y update
RUN apt-get install -y software-properties-common python-software-properties
RUN add-apt-repository ppa:chris-lea/redis-server
RUN apt-get -y update
RUN apt-get -y install redis-server redis-tools

VOLUME [ "/var/lib/redis", "/var/log/redis" ]

EXPOSE 6379
CMD []

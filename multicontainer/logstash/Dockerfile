FROM ubuntu:14.04
MAINTAINER Eder Roger <eder.roger.souza@gmail.com>
ENV REFRESHED_AT 2014-06-01

RUN apt-get -y update
RUN apt-get -y install wget
RUN wget -O - http://packages.elasticsearch.org/GPG-KEY-elasticsearch |apt-key add -
RUN echo 'deb http://packages.elasticsearch.org/logstash/1.4/debian stable main' > /etc/apt/sources.list.d/logstash.list '
RUN apt-get -y update
RUN apt-get -y install logstash

ADD logstash.conf /etc/

WORKDIR /opt/logstash

ENTRYPOINT [ "bin/logstash" ]
CMD [ "--config=/etc/logstash.conf" ]

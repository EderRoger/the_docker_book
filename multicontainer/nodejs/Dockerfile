FROM ubuntu:14.04
MAINTAINER Eder Roger <eder.roger.souza@gmail.com>
ENV REFRESHED_AT 2014-06-01

RUN apt-get -y update
RUN apt-get -y install nodejs npm
RUN ln -s /usr/bin/nodejs /usr/bin/node
RUN mkdir -p /var/log/nodeapp

ADD nodeapp /opt/nodeapp

WORKDIR /opt/nodeapp
RUN npm install

VOLUME [ "/var/log/nodeapp" ]

EXPOSE 3000

ENTRYPOINT [ "nodejs", "server.js" ]

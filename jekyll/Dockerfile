FROM ubuntu:14.04
MAINTAINER Eder Roger "eder.roger.souza@gmail.com"
ENV REFRESHED_AT 2014-06-01

RUN apt-get -y update
RUN apt-get -y install ruby ruby-dev make nodejs
RUN gem install --no-rdoc --no-ri jekyll

VOLUME /data
VOLUME /var/www/html
WORKDIR /data

ENTRYPOINT [ "jekyll", "build", "--destination=/var/www/html" ]

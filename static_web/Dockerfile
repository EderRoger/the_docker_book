# Version: 0.0.1

FROM ubuntu:14.04
MAINTAINER Eder Roger "eder.roger.souza@gmail.com"
RUN apt-get update
RUN apt-get install -y nginx
RUN echo 'Hi, I am in your container' >/usr/share/nginx/html/index.html
LABEL version="1.0"
LABEL location="New York" type="Data Center" role="Web Server"
ENTRYPOINT ["/usr/sbin/nginx"]
EXPOSE 80

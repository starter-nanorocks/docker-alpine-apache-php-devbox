FROM alpine:latest

# Who am I ?
MAINTAINER Andrej Nankov

# Install bash
RUN apk add --update bash && rm -rf /var/cache/apk/*

# For service control
RUN apk add openrc

# Update and upgrade
RUN apk update && apk upgrade

# Install apache2 and php7 module
RUN apk add apache2 php7-apache2

# Install php
RUN apk add php7 php7-fpm php7-opcache

# Php modules
RUN apk add php7-gd php7-mysqli php7-zlib php7-curl php7-session

# Add new apache config -- Fix this
COPY docker/server/httpd-apache2.conf /etc/apache2/httpd.conf

# Copy project 
COPY src/ /var/www/localhost/

WORKDIR /var/www

RUN rm -rf /var/cache/apk/*
ENTRYPOINT ["httpd"] 
CMD ["-D", "FOREGROUND"]

# to build use:
# docker build -t nanorocks/alpine-devbox -f docker/server/Dockerfile .

# to run:
# docker run -d -v $(pwd)/src:/var/www/localhost/ --name apache -p 80:80 nanorocks/alpine-devbox
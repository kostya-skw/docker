# Version: 0.0.1
FROM centos:centos7
MAINTAINER Shirkin Kostya <kostya.skw@gmail.com>

RUN yum install epel-release -y
RUN yum -y update && yum clean all
RUN yum -y install php-fpm && yum clean all
RUN yum -y install nginx

ADD nginx.conf /etc/nginx/nginx.conf
ADD default.conf /etc/nginx/conf.d/default.conf
RUN echo "daemon off;" >> /etc/nginx/nginx.conf

RUN mkdir -p /var/www

EXPOSE 80

#VOLUME ["/var/www"]

ENTRYPOINT /usr/sbin/nginx

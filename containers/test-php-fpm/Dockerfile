# Version: 0.0.1
FROM centos:centos7
MAINTAINER Shirkin Kostya <kostya.skw@gmail.com>

RUN yum install epel-release -y
RUN yum -y update && yum clean all
RUN yum -y install php-fpm && yum clean all
RUN sed -e 's/127.0.0.1:9000/9000/' \
        -e '/allowed_clients/d' \
        -e '/catch_workers_output/s/^;//' \
        -e '/error_log/d' \
        -i /etc/php-fpm.d/www.conf

RUN mkdir -p /var/www

EXPOSE 9000

#VOLUME ["/var/www"]

ENTRYPOINT /usr/sbin/php-fpm --nodaemonize

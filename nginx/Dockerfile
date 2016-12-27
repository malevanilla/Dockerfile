# Version 0.0.1
FROM centos:7
MAINTAINER Alan Chu "malevanilla@gmail.com"
ENV WEB_DOCUMENT_ROOT /srv/www
ENV WEB_DOCUMENT_INDEX index.php

COPY conf/nginx.repo /etc/yum.repos.d/

RUN yum update -y
RUN yum install -y nginx

RUN sed '8 idaemon off;' -i /etc/nginx/nginx.conf

COPY conf/www.conf /etc/nginx/conf.d/
RUN rm -f /etc/nginx/conf.d/default.conf
CMD systemctl enable nginx
CMD ["nginx"]
EXPOSE 80 443


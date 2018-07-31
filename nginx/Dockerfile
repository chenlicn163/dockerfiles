FROM hub.c.163.com/public/centos:7.2-tools
COPY conf/nginx.repo /etc/yum.repos.d/
RUN yum -y install gcc gcc-c++ autoconf pcre pcre-devel make automake && \
	yum -y install wget httpd-tools vim && \
    yum -y install nginx



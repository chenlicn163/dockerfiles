FROM hub.c.163.com/public/centos:7.2-tools
COPY conf/OpenResty.repo  /etc/yum.repos.d
RUN rpm -Uvh https://mirror.webtatic.com/yum/el7/epel-release.rpm
RUN rpm -Uvh https://mirror.webtatic.com/yum/el7/webtatic-release.rpm
RUN yum -y install glibc-static telnet bridge-utils net-tools \
    gcc gcc-c++ autoconf pcre pcre-devel make automake wget httpd-tools vim \
    php56w php56w-devel php56w-gd.x86_64 \
	php56w-ldap.x86_64 php56w-mbstring.x86_64 php56w-mcrypt.x86_64 php56w-mysql.x86_64 \
	php56w-pdo.x86_64 php56w-opcache.x86_64  php56w-xml.x86_64 php56w-fpm  && \
    /bin/echo 'root:123456'|chpasswd

RUN yum -y install openresty && \
    useradd nginx && mkdir /usr/local/openresty/nginx/conf/conf.d && \
    mkdir /var/log/nginx
COPY conf/nginx/nginx.conf  /usr/local/openresty/nginx/conf
COPY conf/nginx/default.conf  /usr/local/openresty/nginx/conf/conf.d
COPY conf/init.sh      /var
EXPOSE 22
EXPOSE 80
EXPOSE 443
ENTRYPOINT ["/bin/bash", "/var/init.sh"]
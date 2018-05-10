FROM hub.c.163.com/public/centos:6.7-tools
RUN rpm -Uvh http://mirror.webtatic.com/yum/el6/latest.rpm
RUN yum -y update && yum -y install php56w php56w-devel php56w-gd.x86_64 \
php56w-ldap.x86_64 php56w-mbstring.x86_64 php56w-mcrypt.x86_64 php56w-mysql.x86_64 \
php56w-pdo.x86_64 php56w-opcache.x86_64  php56w-xml.x86_64 php56w-fpm nginx
RUN mkdir -p /var/www && mkdir -p /run
RUN curl -sS https://getcomposer.org/installer | php && mv composer.phar /usr/local/bin/composer
COPY ./index.php	/var/www
COPY ./default.conf /etc/nginx/conf.d
COPY ./nginx.conf	/etc/nginx
COPY ./php.ini     /etc
COPY ./www.conf     /etc/php-fpm.d
COPY ./init.sh      /var
EXPOSE 80
ENTRYPOINT ["/bin/bash", "/var/init.sh"]
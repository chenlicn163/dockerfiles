FROM registry.cn-hangzhou.aliyuncs.com/pinguo-ops/php-msf-docker:latest

RUN cd /var/tmp && git clone https://gitee.com/swoole/swoole.git && \
cd swoole && /home/worker/php/bin/phpize \
./configure --with-php-config=/home/worker/php/bin/php-config --enable-async-redis


ENTRYPOINT ["/run.sh"]

EXPOSE 22 80 443
CMD ["/usr/sbin/sshd", "-D"]
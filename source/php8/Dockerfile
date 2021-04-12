FROM php:8.0.3-fpm
RUN sed -i 's#http://deb.debian.org#https://mirrors.163.com#g' /etc/apt/sources.list
COPY install-php-extensions /usr/local/bin/
RUN chmod +x /usr/local/bin/install-php-extensions && sync && \
    install-php-extensions zip gd bcmath bz2 exif ffi imagick mysqli opcache pcntl pdo_mysql
RUN install-php-extensions grpc mcrypt memcache memcached mongodb msgpack protobuf redis swoole yaml
RUN install-php-extensions @composer-2.0.2
RUN composer config -g repos.packagist composer https://mirrors.aliyun.com/composer/
RUN useradd --create-home --no-log-init --shell /bin/bash avrilko && adduser avrilko sudo && echo 'avrilko:123456' | chpasswd && echo 'root:123456' | chpasswd
USER avrilko:avrilko
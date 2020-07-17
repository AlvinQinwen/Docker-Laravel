FROM php:7.3-fpm
RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libpng-dev \
    && docker-php-ext-install -j$(nproc) iconv \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j$(nproc) gd \
    && pecl install swoole \
    && pecl install redis \
    && docker-php-ext-enable swoole redis

RUN docker-php-ext-install pdo_mysql pdo mysqli

#RUN \
#  curl 'http://pecl.php.net/get/redis-3.1.5.tgz' -o /tmp/redis-3.1.5.tgz  \
#  && cd /tmp \
#  && pecl install redis-3.1.5.tgz \
#  && rm -rf redis-3.1.5.tgz \
#  && docker-php-ext-enable redis \
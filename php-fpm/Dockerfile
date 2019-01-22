FROM php:7.3.1-fpm

RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libpng-dev \
        libmagickcore-6.q16-dev libmagickwand-6.q16-dev \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j$(nproc) \
        gd \
        mysqli \
        pdo_mysql

RUN pecl install \
    && pecl install \
        xdebug-2.7.0beta1 \
    && docker-php-ext-enable \
        xdebug

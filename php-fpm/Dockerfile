######
# See: https://hub.docker.com/_/php/
######

FROM php:7.3.0-fpm

######
# You can install php extensions using docker-php-ext-install
######

# RUN apt-get update && apt-get install -y \
#         libfreetype6-dev \
#         libjpeg62-turbo-dev \
#         libmcrypt-dev \
#         libpng12-dev \
#     && docker-php-ext-install -j$(nproc) iconv mcrypt \
#     && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
#     && docker-php-ext-install -j$(nproc) gd
RUN pecl install \
    && pecl install xdebug-2.7.0beta1 \
    && docker-php-ext-enable xdebug

# COPY docker-php-ext-xdebug.ini /usr/local/etc/php/conf.d/

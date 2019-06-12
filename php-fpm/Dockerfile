FROM php:7.3.6-fpm-stretch

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
        xdebug-2.7.2 \
    && docker-php-ext-enable \
        xdebug

RUN echo 'xdebug.remote_enable = 1' >> /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini \ 
    && echo 'xdebug.remote_autostart = 1' >> /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini \ 
    && echo 'xdebug.idekey = "vscode"' >> /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini \ 
    && echo 'xdebug.default_enable = 1' >> /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini \ 
    # && echo 'xdebug.remote_host = docker.for.win.localhost' >> /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini \ 
    && echo 'xdebug.remote_host = host.docker.internal' >> /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini \ 
    && echo 'xdebug.var_display_max_children = -1' >> /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini \ 
    && echo 'xdebug.var_display_max_children = -1' >> /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini \ 
    && echo 'xdebug.var_display_max_depth = -1' >> /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini \ 
    && echo 'xdebug.remote_port = 9009' >> /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini

FROM php:7.3-fpm

RUN apt-get update && apt-get upgrade -y \
    && apt-get install -y \
    curl \
    wget \
    zip \
    unzip \
    zlib1g-dev libzip-dev \
    libfreetype6-dev \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ \
    && docker-php-ext-install -j$(nproc) gd \
    && docker-php-ext-install pdo pdo_mysql mysqli zip \
    && if ! pecl list | grep xdebug; \
           then \
               pecl install xdebug \
               && docker-php-ext-enable xdebug; \
           fi
RUN docker-php-ext-install gd
RUN echo 'xdebug.remote_port=9000' >> /usr/local/etc/php/php.ini
RUN echo 'xdebug.remote_enable=1' >> /usr/local/etc/php/php.ini
RUN echo 'xdebug.remote_connect_back=1' >> /usr/local/etc/php/php.ini

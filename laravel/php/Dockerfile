FROM php:fpm

RUN apt-get update \
    # gd
    && apt-get install -y --no-install-recommends libfreetype6-dev libjpeg-dev libpng12-dev \
    && docker-php-ext-install gd \
    # redis
    && pecl install redis \
    && docker-php-ext-enable redis \
    # pdo_mysql
    && docker-php-ext-install pdo_mysql \
    # opcache
    && docker-php-ext-enable opcache \
    # xdebug
    && pecl install xdebug \
    && docker-php-ext-enable xdebug \
    # clean up
    && apt-get autoclean -y \
    && rm -rf /var/lib/apt/lists/* \
    && rm -rf /tmp/pear/

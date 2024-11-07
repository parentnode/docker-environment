FROM php:8.2-apache

RUN apt-get update \
    && apt-get install -y zip libzip-dev libcurl4-openssl-dev libonig-dev libmagickcore-dev libmagickwand-dev \
    && pecl install redis imagick igbinary \
    && docker-php-ext-install mysqli xml zip curl mbstring \
    && docker-php-ext-enable redis imagick mysqli xml zip igbinary curl mbstring \
    && a2enmod rewrite \
    && a2enmod ssl \
    && a2enmod headers

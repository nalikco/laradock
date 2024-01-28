FROM php:8.3.1-fpm

ENV COMPOSER_ALLOW_SUPERUSER=1

COPY --from=composer:latest /usr/bin/composer /usr/local/bin/composer

RUN apt-get update -y && \
    apt-get install wget libpq-dev libzip-dev libpng-dev libjpeg-dev git curl nodejs zip -y && \
    docker-php-ext-install pdo zip pdo_pgsql && docker-php-ext-configure gd --with-jpeg && docker-php-ext-install -j$(nproc) gd

WORKDIR /var/www/app

COPY . ./

RUN composer install

RUN chown -R $USER:www-data storage && chown -R $USER:www-data bootstrap/cache && chmod -R 775 storage && chmod -R 775 bootstrap/cache

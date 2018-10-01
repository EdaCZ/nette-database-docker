FROM php:7.2-cli

RUN apt-get update && apt-get install -y libjpeg62-turbo-dev libjpeg-dev libpng-dev libfreetype6-dev libgd-dev libmcrypt-dev mysql-client

RUN docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/

RUN docker-php-ext-install pdo_mysql mysqli gd exif

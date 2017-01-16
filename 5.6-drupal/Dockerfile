FROM php:5.6-fpm
COPY php.ini /usr/local/etc/php/
RUN apt-get update && apt-get install -y \
    libfreetype6-dev \
    libjpeg62-turbo-dev \
    libjpeg-dev \
    libpq-dev \
    libmcrypt-dev \
    libpng12-dev \
    libssl-dev \
    libc-client-dev \
    libkrb5-dev \
    libgmp-dev \
    re2c \
    libmhash-dev \
    php5-mysql \
    cron \
    zlib1g-dev \
    libmemcached-dev \
&& docker-php-ext-install iconv mcrypt \
&& docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
&& docker-php-ext-install gd \
&& docker-php-ext-configure imap --with-kerberos --with-imap-ssl \
&& docker-php-ext-install imap \
&& ln -s /usr/include/x86_64-linux-gnu/gmp.h /usr/local/include/ \
&& docker-php-ext-install gmp \
&& docker-php-ext-install mysql mbstring pdo pdo_mysql pdo_pgsql zip \
&& pecl install memcached-2.2.0 \
&& docker-php-ext-enable memcached


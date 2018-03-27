FROM php:fpm

RUN apt-get update && apt-get install -y \
        git \
        zip \
        unzip \
        zlib1g-dev \
        libzip-dev \
        libfreetype6-dev \
	    libjpeg62-turbo-dev \
        libxml2-dev \
    && docker-php-ext-install -j$(nproc) iconv \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-configure soap --enable-soap \
    && docker-php-ext-configure pdo_mysql --with-pdo-mysql \
    && docker-php-ext-configure mbstring --enable-mbstring \
    && docker-php-ext-install zip pdo pdo_mysql \
       dom   \
       iconv \
       gd \
       mbstring \
       soap \
    && pecl install xdebug \
    && docker-php-ext-enable xdebug

# install composer
RUN curl -sS https://getcomposer.org/installer | php -- --filename=composer --install-dir=/bin
WORKDIR /var/www/html 
COPY . /var/www/html/

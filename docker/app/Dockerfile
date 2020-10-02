FROM php:7.4-apache

 # 1. Add php.ini, 000-default.conf to ubuntu folder
 ADD php.ini /usr/local/etc/php
 ADD 000-default.conf /etc/apache2/sites-enabled/

 # 2. Install Development Packages
 RUN apt-get update \
 && apt-get install -y \
 git \
 zip \
 curl \
 unzip \
 vim \
 libpng-dev \
 libpq-dev \
 && docker-php-ext-install pdo_mysql

 # 3. Install Composer
 COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

 # 4. mod_rewrite for URL rewrite and mod_headers for .htaccess extra headers like Access-Control-Allow-Origin-

 # 5. Disable modRewrite for Laravel
 RUN mv /etc/apache2/mods-available/rewrite.load /etc/apache2/mods-enabled
 # RUN a2enmod rewrite headers
 # RUN /bin/sh -c a2enmod rewrite

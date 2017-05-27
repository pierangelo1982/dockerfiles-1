FROM php:7-apache
MAINTAINER shimomo <yuichi@shimomo.net>

WORKDIR /var/www/html

COPY ./config/000-default.conf /etc/apache2/sites-available/000-default.conf

RUN apt-get update && \
  apt-get -y install curl git libicu-dev libpq-dev zlib1g-dev zip && \
  docker-php-ext-install intl mbstring pcntl pdo_mysql pdo_pgsql zip && \
  usermod -u 1000 www-data && \
  usermod -a -G users www-data && \
  chown -R www-data:www-data /var/www && \
  curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer && \
  composer create-project --prefer-dist cakephp/app cakephp && \
  a2enmod rewrite

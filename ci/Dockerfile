FROM php:5.6-cli
MAINTAINER Matthieu Mota <matthieumota@gmail.com>

RUN apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y \
	capistrano \
	php5-mysql \
	phpunit \
	git \
	zip

RUN docker-php-ext-install \
	pdo_mysql

ADD https://getcomposer.org/composer.phar /usr/local/bin/composer
RUN chmod +x /usr/local/bin/composer

ADD php.ini /usr/local/etc/php/

RUN rm -rf /var/lib/apt/lists/* \
  apt-get clean
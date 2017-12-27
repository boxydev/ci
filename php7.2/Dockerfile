FROM php:7.2
MAINTAINER Matthieu Mota <matthieumota@gmail.com>

RUN apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y \
    zip \
    unzip \
    zlib1g-dev

RUN docker-php-ext-install \
    zip

ADD https://getcomposer.org/composer.phar /usr/local/bin/composer
RUN chmod 755 /usr/local/bin/composer

RUN rm -rf /var/lib/apt/lists/* \
  apt-get clean

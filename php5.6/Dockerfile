FROM php:5.6
MAINTAINER Matthieu Mota <matthieumota@gmail.com>

RUN apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y \
	ruby \
	git \
	zip

RUN docker-php-ext-install \
	pdo_mysql

RUN curl -sL https://deb.nodesource.com/setup_4.x | bash - \
	&& \
	apt-get install -y \
	nodejs

ADD https://getcomposer.org/composer.phar /usr/local/bin/composer
RUN chmod 755 /usr/local/bin/composer

ADD php.ini /usr/local/etc/php/

RUN npm install -g bower grunt-cli
RUN gem install capistrano

RUN rm -rf /var/lib/apt/lists/* \
  apt-get clean

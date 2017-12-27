FROM php:7.2
MAINTAINER Matthieu Mota <matthieumota@gmail.com>

RUN apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y \
    zip \
    unzip \
    zlib1g-dev \
    gnupg

RUN docker-php-ext-install \
    zip

RUN curl -sL https://deb.nodesource.com/setup_9.x | bash - \
    && \
    apt-get install -y \
    nodejs

RUN curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
RUN echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list

RUN apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y \
    yarn

ADD https://getcomposer.org/composer.phar /usr/local/bin/composer
RUN chmod 755 /usr/local/bin/composer

RUN rm -rf /var/lib/apt/lists/* \
    apt-get clean

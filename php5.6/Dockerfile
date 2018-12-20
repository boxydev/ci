FROM php:5.6
MAINTAINER Matthieu Mota <matthieumota@gmail.com>

RUN groupadd -g 1000 boxydev \
    && useradd -u 1000 -g 1000 -m -s /bin/bash boxydev

RUN apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y \
    git \
    gnupg \
    libzip-dev \
    unzip \
    zlib1g-dev

RUN docker-php-ext-install \
    zip \
    pdo_mysql

RUN curl -sL https://deb.nodesource.com/setup_11.x | bash - \
    && \
    DEBIAN_FRONTEND=noninteractive apt-get install -y \
    nodejs

RUN curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add -
RUN echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list
 
RUN apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y \
    yarn

RUN php -r "readfile('https://getcomposer.org/installer');" | php -- --install-dir=/usr/local/bin --filename=composer \
    && \
    chmod +x /usr/local/bin/composer

RUN wget https://cs.sensiolabs.org/download/php-cs-fixer-v2.phar -O /usr/local/bin/php-cs-fixer \
    && \
    chmod +x /usr/local/bin/php-cs-fixer

RUN rm -rf /var/lib/apt/lists/* \
    apt-get clean

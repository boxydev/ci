FROM php:7.2
MAINTAINER Matthieu Mota <matthieumota@gmail.com>

RUN apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y \
    git gnupg libicu-dev libxslt1-dev \
    libzip-dev rsync unzip zlib1g-dev

RUN docker-php-ext-install bcmath intl pdo_mysql xsl zip \
    && pecl install redis && docker-php-ext-enable redis

RUN curl -sL https://deb.nodesource.com/setup_14.x | bash - \
    && DEBIAN_FRONTEND=noninteractive apt-get install -y nodejs

RUN curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add - \
    && echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list \
    && apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y yarn \
    && rm -rf /var/lib/apt/lists/*

RUN php -r "readfile('https://getcomposer.org/installer');" | php -- --install-dir=/usr/local/bin --filename=composer \
    && chmod +x /usr/local/bin/composer

RUN curl -L https://cs.symfony.com/download/php-cs-fixer-v2.phar -o /usr/local/bin/php-cs-fixer \
    && chmod +x /usr/local/bin/php-cs-fixer

RUN cp $PHP_INI_DIR/php.ini-development $PHP_INI_DIR/php.ini
COPY php.ini $PHP_INI_DIR/conf.d

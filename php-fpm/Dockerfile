FROM ubuntu:18.04

RUN apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get install --no-install-recommends -y \
	unzip \
        curl \
        php-fpm \
        php-apcu \
        php-ctype \
        php-curl \
        php-dom \
        php-fileinfo \
        php-ftp \
        php-iconv \
        php-json \
        php-mbstring \
        php-mysql \
	php-mysqli \
        php-mysqlnd \
        php-pdo \
        php-pear \
        php-phar \
        php-posix \
        php-simplexml \
        php-tokenizer \
        php-xml \
        php-zip \
        php-xdebug \
        php-sqlite3 \
        php-intl \
	mysql-client \
        composer \
        wget \
        git \
        ssh \
        nodejs \
        npm \
	vim 

# FIX permission for PHP
RUN usermod -u 1000 www-data

RUN service php7.2-f pm start

COPY php-fpm.conf /etc/php/7.2/fpm/pool.d/www.conf
COPY php.ini /etc/php/7.0/mods-available/php.ini

RUN npm install npm@latest -g

WORKDIR /etc/php/7.2/fpm/conf.d/
RUN ln -s /etc/php/7.0/mods-available/php.ini 00-php.in


WORKDIR /var/www/html

CMD ["/usr/sbin/php-fpm7.2"]



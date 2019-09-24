FROM julioarteta/php-fpm:7.2
MAINTAINER Julio R. Arteta<julioarteta93@gmail.com>

# FIX permission for PHP
RUN usermod -u 1000 www-data

RUN service php7.2-fpm start

COPY php-fpm.conf /etc/php/7.2/fpm/pool.d/www.conf
COPY php.ini /etc/php/7.0/mods-available/php.ini

RUN npm install npm@latest -g

WORKDIR /etc/php/7.2/fpm/conf.d/
RUN ln -s /etc/php/7.0/mods-available/php.ini 00-php.in


WORKDIR /var/www/html

CMD ["/usr/sbin/php-fpm7.2"]


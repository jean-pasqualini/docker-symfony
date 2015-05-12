FROM debian:latest

MAINTAINER Jean Pasqualini <jpasqualini75@gmail.com>

RUN apt-get update && apt-get install -y php5-common php5-cli php5-fpm php5-mcrypt php5-apcu php5-gd php5-imagick php5-curl php5-intl php5-xsl

RUN apt-get install -y curl wget git imagemagick
RUN curl -sS https://getcomposer.org/installer | php
RUN mv composer.phar /usr/local/bin/composer

ADD symfony.ini /etc/php5/fpm/conf.d/
ADD symfony.ini /etc/php5/cli/conf.d/

ADD symfony.pool.conf /etc/php5/fpm/pool.d/

RUN usermod -u 1000 www-data

CMD ["php5-fpm", "-F"]

EXPOSE 9000

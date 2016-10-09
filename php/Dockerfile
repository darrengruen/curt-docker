FROM debian:jessie
MAINTAINER Darren Green <darren.green@meetingprotocol.com>

RUN apt-get update \
    && apt-get install -y \
    php5 \
    php5-dev \
    php-pear \
    php5-fpm \
    php5-cli \
    php5-mcrypt \
    php5-intl \
    libxrender-dev \
    libfontconfig \
    libxext-dev \
    && pecl install apc \
    && pecl install mongo \
    && usermod -u 1000 www-data

COPY curt.ini /etc/php5/fpm/conf.d/
COPY curt.ini /etc/php5/cli/conf.d/
COPY curt.pool.conf /etc/php5/fpm/pool.d/

CMD [ "php5-fpm", "-F" ]

EXPOSE 9000


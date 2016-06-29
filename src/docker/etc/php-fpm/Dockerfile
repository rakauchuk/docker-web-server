FROM php:5.6.17-fpm

ENV XDEBUG_VERSION 2.2.7
ENV XDEBUG_MD5 71a6b75885207e79762e1e7aaf5c3993

RUN apt-get update && apt-get install -my \
  htop \
  curl \
  git \
  wget \
  vim \
  supervisor \
  php5-dev \
  php5-curl \
  php5-cli \
  php5-fpm \
  php-pear \
  php5-gd \
  php5-memcached \
  php5-redis \
  php5-sqlite \
  php5-mysql \
  php5-pgsql \
  php5-mcrypt \
  php5-intl \
  php5-imap \
  php5-tidy \
  php5-xdebug \
  php-apc

RUN docker-php-ext-install pdo pdo_mysql

RUN set -x \
    && curl -SL "http://www.xdebug.org/files/xdebug-$XDEBUG_VERSION.tgz" -o xdebug.tgz \
    && echo $XDEBUG_MD5 xdebug.tgz | md5sum -c - \
    && mkdir -p /usr/src/xdebug \
    && tar -xf xdebug.tgz -C /usr/src/xdebug --strip-components=1 \
    && rm xdebug.* \
    && cd /usr/src/xdebug \
    && phpize \
    && ./configure \
    && make -j"$(nproc)" \
    && make install \
    && make clean

RUN curl -sS https://getcomposer.org/installer | php \
    && mv composer.phar /usr/local/bin/composer

RUN wget https://phar.phpunit.de/phpunit.phar \
    && chmod +x phpunit.phar \
    && mv phpunit.phar /usr/local/bin/phpunit

RUN phpunit --version

RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

ADD xdebug.ini /usr/local/etc/php/conf.d/
ADD symfony.pool.conf /etc/php5/fpm/pool.d/

RUN usermod -u 1000 www-data

RUN curl -LsS https://symfony.com/installer -o /usr/local/bin/symfony
RUN chmod a+x /usr/local/bin/symfony

VOLUME /var/www/symfony

CMD ["php-fpm", "-F"]

EXPOSE 9000

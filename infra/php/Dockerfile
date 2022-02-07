FROM php:7.4.27-apache
SHELL ["/bin/bash", "-oeux", "pipefail", "-c"]

ENV COMPOSER_ALLOW_SUPERUSER=1 \
  COMPOSER_HOME=/composer

COPY --from=composer:2.0 /usr/bin/composer /usr/bin/composer

RUN apt-get update && \
  apt-get -y install git unzip libzip-dev libicu-dev libonig-dev && \
  # GD 用
  apt-get -y install libfreetype6-dev libjpeg62-turbo-dev libwebp-dev && \
  # コンテナ内動作確認用
  apt-get -y install iputils-ping net-tools vim && \
  apt-get clean && \
  rm -rf /var/lib/apt/lists/* && \
  docker-php-ext-install intl pdo_mysql mysqli zip bcmath exif && \
  # GD 用
  docker-php-ext-configure gd --with-freetype --with-jpeg --with-webp && \
  docker-php-ext-install -j$(nproc) gd

RUN pecl install xdebug && \
  docker-php-ext-enable xdebug

RUN a2enmod rewrite authz_groupfile

COPY ./php.ini /usr/local/etc/php/php.ini

WORKDIR /work
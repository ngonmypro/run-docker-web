FROM php:7.1-fpm

RUN apt-get update \
    && apt-get install -y \
    cron \
    libfreetype6-dev \
    libicu-dev \
    libjpeg62-turbo-dev \
    libmcrypt-dev \
    libpq-dev \
    # libpng12-dev \
    libxslt1-dev \
    openssh-server \
    openssh-client \
    rsync

RUN docker-php-ext-configure \
  gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ 

RUN docker-php-ext-install \
  bcmath \
  gd \
  intl \
  mbstring \
  mcrypt \
  pdo \ 
  pdo_pgsql \ 
  pdo_mysql \
  soap \
  xsl \
  zip

RUN curl -sS https://getcomposer.org/installer | \
  php -- --install-dir=/usr/local/bin --filename=composer

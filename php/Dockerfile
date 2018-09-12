FROM php:7.1-apache

RUN apt-get update -qq && apt-get install -y -qq apt-utils && mkdir -p /usr/share/man/man1 \
    && apt-get update -qq && apt-get install -y -qq openjdk-8-jre-headless \
    && apt-get update -qq && apt-get install -y -qq  openjdk-8-jdk && dpkg --configure -a

RUN apt-get update -qq && apt-get install -y -qq \
        libicu-dev \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libmcrypt-dev \
        libpng-dev \
        libcurl4-openssl-dev \
        software-properties-common  \
        libcurl3 curl \
        git \
        zip \
        unzip \
        inotify-tools \
        build-essential \
        libxml2-dev libxslt1-dev zlib1g-dev \
        git \
        mysql-client \
        sshpass \
        gnupg \
        nano \
        sudo \
        vim \
        graphviz \
        netcat-openbsd \
        ant

RUN docker-php-ext-install iconv mcrypt mbstring opcache \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install gd \
    && docker-php-ext-install zip \
    && docker-php-ext-install curl \
    && docker-php-ext-install intl \
    && docker-php-ext-install pdo \
    && docker-php-ext-install pdo_mysql

RUN a2enmod rewrite && a2enmod actions


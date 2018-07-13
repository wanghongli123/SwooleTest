FROM php:7.1-fpm-alpine

RUN apk update && apk add --no-cache \
    libbsd \
    libxml2-dev \
    sqlite-dev \
    curl-dev \
    libpng-dev \
    libjpeg-turbo-dev \
    freetype-dev && \
    rm -rf /tmp/* && \
    rm -rf /var/cache/apk/*

# Configure PHP extensions
RUN docker-php-ext-configure json && \
    docker-php-ext-configure session && \
    docker-php-ext-configure ctype && \
    docker-php-ext-configure tokenizer && \
    docker-php-ext-configure simplexml && \
    docker-php-ext-configure dom && \
    docker-php-ext-configure mbstring && \
    docker-php-ext-configure zip && \
    docker-php-ext-configure pdo && \
    docker-php-ext-configure pdo_sqlite && \
    docker-php-ext-configure pdo_mysql && \
    docker-php-ext-configure curl && \
    docker-php-ext-configure iconv && \
    docker-php-ext-configure xml && \
    docker-php-ext-configure phar && \
    docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/

# Build and install PHP extensions
RUN docker-php-ext-install json \
    session \
    ctype \
    tokenizer \
    simplexml \
    dom \
    mbstring \
    zip \
    pdo \
    pdo_sqlite \
    pdo_mysql \
    curl \
    iconv \
    xml \
    gd

RUN apk --no-cache --update add \
    zip \
    unzip \
    openssl-dev \
    autoconf \
    gcc \
    g++ \
    bash \
    make \
    pcre-dev && \
    rm -rf /tmp/* && \
    rm -rf /var/cache/apk/*

RUN /bin/bash -lc "pecl install swoole"
ARG INI_FILE
COPY ${INI_FILE} /usr/local/etc/php/conf.d/php.ini
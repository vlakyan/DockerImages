FROM php:7.4-cli

WORKDIR /srv

RUN apt update \
    && apt install -y git zip libssh2-1-dev rsync sshpass \
    && pecl install ssh2-1.2 \
    && pecl install xdebug-2.9.0 \
    && docker-php-ext-enable ssh2 \
    && docker-php-ext-install pdo_mysql \
    && php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" \
    && php composer-setup.php --install-dir=/bin --filename=composer \
    && php -r "unlink('composer-setup.php');"

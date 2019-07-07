FROM ubuntu:19.04

ENV DEBIAN_FRONTEND noninteractive

WORKDIR /srv

RUN apt-get -qq update \
    && apt -y install --no-install-recommends software-properties-common \
    && add-apt-repository ppa:ondrej/php \
    && apt -y clean \
    && rm -rf /var/lib/apt/lists/*

RUN apt -qq update \
    && apt -y install --no-install-recommends git ca-certificates ghostscript gsfonts zip unzip ssh \
    && apt -y install --no-install-recommends php-pear php7.3-dev php7.3-curl php7.3-gd php7.3-imap php7.3-intl \
        php7.3-mbstring php7.3-mysql php7.3-soap php7.3-sqlite3 php7.3-xml php7.3-zip php7.3-bcmath php7.3-yaml \
        php7.3-cli php-apcu php-imagick php-memcache php-redis php-ssh2 php-igbinary libxrender1 \
    && apt -y autoremove \
    && apt -y clean \
    && rm -rf /var/lib/apt/lists/* \
    && update-alternatives --set php /usr/bin/php7.3

RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" \
    && php composer-setup.php \
    && php -r "unlink('composer-setup.php');" \
    && mv composer.phar /usr/local/bin/composer \
    && composer clear-cache
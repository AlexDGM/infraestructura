FROM ubuntu:22.04

LABEL maintainer="Alex G" author="Alex G" \
description="DockerFile Vtiger"

RUN apt-get update && apt-get install -y \
    apache2 \
    php \
    libapache2-mod-php \
    php-cli \
    php-common \
    php-curl \
    php-zip \
    php-gd \
    php-mysql \
    php-xml \
    php-mbstring \
    php-json \
    php-intl \
    php-imap \
    wget \
    tar \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /var/www/html/
RUN wget -O vtigercrm.tar.gz https://sourceforge.net/projects/vtigercrm/files/vtiger%20CRM%208.4.0/Core%20Product/vtigercrm8.4.0.tar.gz/download
RUN tar -xzvf vtigercrm.tar.gz
RUN a2enmod rewrite
RUN chown -R www-data:www-data /var/www/html/vtigercrm
RUN chmod -R 775 /var/www/html/vtigercrm/

CMD ["apachectl", "D", "FOREGROUND"]
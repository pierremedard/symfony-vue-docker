FROM php:8.2-apache

RUN echo "ServerName localhost" >> /etc/apache2/apache2.conf

RUN curl -sSk https://getcomposer.org/installer | php -- --disable-tls && \
   mv composer.phar /usr/local/bin/composer

RUN apt-get update && docker-php-ext-install mysqli pdo_mysql

RUN curl -1sLf 'https://dl.cloudsmith.io/public/symfony/stable/setup.deb.sh' | bash
RUN apt install -y git zip unzip symfony-cli

RUN git config --global user.email "dev.pierre.medard@gmail.com" && \
   git config --global user.name "Pierre Medard" && \
   git config --global --add safe.directory *

WORKDIR /var/www

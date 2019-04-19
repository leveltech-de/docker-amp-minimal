FROM php:7.2-apache

RUN a2enmod alias
RUN a2enmod rewrite
RUN a2enmod expires
RUN a2enmod headers
RUN a2enmod deflate
RUN a2enmod ssl

RUN openssl req \
    -x509 \
    -nodes \
    -days 365 \
    -newkey rsa:2048 \
    -keyout /etc/ssl/private/apache-selfsigned.key \
    -out /etc/ssl/certs/apache-selfsigned.crt \
    -subj "/C=IE/ST=Co Limerick/L=Limerick/O=Dis/CN=localhost"

RUN docker-php-ext-install mysqli pdo pdo_mysql

COPY files/ /
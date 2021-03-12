FROM ubuntu:18.04

RUN apt-get update \
    && apt-get install -y apache2 \
    && apt-get -y install libapache2-mod-fcgid \
    && a2enmod proxy_fcgi \
    && git clone https://github.com/deaw-birt/despliegue-PHP.git

COPY 000-default.conf /etc/apache2/sites-available

COPY despliegue-PHP/php/index.html /var/www/html
COPY despliegue-PHP/php/dwes.css /var/www/html

RUN rm despliegue-PHP/

EXPOSE 80
CMD ["apachectl", "-D", "FOREGROUND"]
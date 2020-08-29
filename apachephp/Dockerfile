FROM ubuntu
MAINTAINER Jo Vandeginste "jo.vandeginste@gmail.com"

ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get update \
 && apt-get -y install ca-certificates curl libxml2 apache2 php php-mysql php-gd php-curl php-sqlite3 php-xml ssmtp mailutils \
 && rm -rf /var/lib/apt/lists/* # 20140918

RUN rm -rf /var/www/html \
 && mkdir -p /var/lock/apache2 /var/run/apache2 /var/log/apache2 /var/www/html \
 && chown -R www-data:www-data /var/lock/apache2 /var/run/apache2 /var/log/apache2 /var/www/html

RUN a2enmod rewrite

ADD apache2.conf /etc/apache2/apache2.conf
ADD ssmtp.conf /etc/ssmtp/ssmtp.conf

WORKDIR /var/www/html

EXPOSE 80
CMD ["apache2", "-DFOREGROUND"]

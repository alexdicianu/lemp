FROM ubuntu:14.04
MAINTAINER alex dicianu "alex.dicianu@gmail.com"
RUN apt-get update --fix-missing

# PHP 5
RUN apt-get install -y vim curl wget git build-essential python-software-properties 
RUN apt-get install -y php5 php5-cgi php5-fpm php5-cli php5-mysql php5-curl php5-gd php5-mcrypt php5-intl php5-imap php5-tidy php-pear php5-dev strace php5-apcu

# MySQL
RUN apt-get install -y mysql-client
RUN apt-get install -y make

# Drush requires composer.
RUN curl -sS https://getcomposer.org/installer | php
RUN mv composer.phar /usr/local/bin/composer
RUN ln -s /usr/local/bin/composer /usr/bin/composer

RUN mkdir /usr/drush/
RUN git clone https://github.com/drush-ops/drush.git /usr/drush/
RUN chmod u+x /usr/drush/drush
RUN ln -s /usr/drush/drush /usr/bin/drush

WORKDIR /usr/drush
RUN composer install
WORKDIR /var/www/html/

# PHP (adding Pantheon php.ini and php-fpm.conf to the mix)
ADD php/php.ini /etc/php5/fpm/php.ini
ADD php/php.ini /etc/php5/cli/php.ini
ADD php/php-fpm.conf /etc/php5/fpm/pool.d/www.conf

# nginx
RUN apt-get -y -q install nginx
RUN mkdir -p /var/www/html

ADD nginx/sites/ /etc/nginx/conf.d/
ADD nginx/nginx.conf /etc/nginx/nginx.conf

# run.sh
ADD bin/run.sh /etc/run.sh
RUN chmod a+x /etc/run.sh

EXPOSE 8088

ENTRYPOINT /etc/run.sh
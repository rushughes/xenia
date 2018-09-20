FROM nginx:latest

COPY    nginx.conf /etc/nginx/nginx.conf
RUN	mkdir /var/run/php-fpm /var/www /var/www/html
RUN	chown www-data: /var/run/php-fpm

VOLUME ["/var/www/html", "/usr/local/etc/php-fpm.d", "/var/run/php-fpm", "/etc/nginx/conf.d"]

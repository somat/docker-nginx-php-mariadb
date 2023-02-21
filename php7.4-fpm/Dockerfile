FROM php:7.4.33-fpm-alpine

RUN apk add --no-cache supervisor nginx
# Add libraries
RUN docker-php-ext-install mysqli pdo pdo_mysql

COPY supervisord-app.conf /etc/supervisord.conf
COPY zzzz-docker.conf /usr/local/etc/php-fpm.d/zzzz-docker.conf
COPY default.conf /etc/nginx/http.d/default.conf

CMD ["/usr/bin/supervisord", "-n", "-c", "/etc/supervisord.conf"]

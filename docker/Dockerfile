FROM php:fpm-alpine
MAINTAINER azure <https://baiyue.one>

COPY docker-entrypoint.sh php.ini default.conf /
RUN apk add --no-cache \
        git \
        bash \
        nginx \
        tzdata && \
    mkdir -p /run/nginx && \
    mv /default.conf /etc/nginx/conf.d && \
    mv /php.ini /usr/local/etc/php && \
    chmod +x /docker-entrypoint.sh && \
    git clone https://github.com/Baiyuetribe/oneindex.git /var/www/html 

# Persistent config file and cache
VOLUME [ "/var/www/html/config", "/var/www/html/cache" ]
ENTRYPOINT [ "/docker-entrypoint.sh" ]
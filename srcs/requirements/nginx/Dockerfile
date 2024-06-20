FROM debian:bullseye

RUN apt update - \
    && apt upgrade -y \
    && apt install -y nginx curl openssl \
    && mkdir -p /etc/nginx/ssl \
    && openssl req -newkey rsa:4096 -x509 -sha256 -days 365 -nodes -out /etc/nginx/ssl/inception.crt -keyout /etc/nginx/ssl/inception.key -subj "/C=FR/ST=IDF/L=Paris/O=42 school/OU=maburnet/CN=maburnet.42.fr/UID=maburnet" \
    && mkdir -p /var/run/nginx \
    && chmod 755 /var/www/html \
    && chown -R www-data:www-data /var/www/html


COPY /conf/nginx.conf /etc/nginx/nginx.conf

EXPOSE 443

CMD [ "nginx", "-g", "daemon off;" ]

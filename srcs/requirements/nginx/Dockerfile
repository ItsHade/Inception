FROM debian:bullseye

#install all the program
RUN		apt-get update
RUN		apt-get install -y nginx \
                openssl

# nginx SSL
RUN mkdir /etc/nginx/ssl
RUN openssl req -newkey rsa:4096 -x509 -sha256 -days 365 -nodes \
       -out /etc/nginx/ssl/maburnet.crt \
       -keyout /etc/nginx/ssl/maburnet.key \
       -subj "/C=FR/ST=Paris/L=Paris/O=42 School/OU=maburnet/CN=maburnet/"

COPY ./conf/nginx.conf /etc/nginx/conf.d

# nginx config
RUN mkdir -p /run/nginx

#the only port allowed
EXPOSE	443

# Start nginx
CMD ["nginx", "-g", "daemon off;"]

# RUN apt update - \
#     && apt upgrade -y \
#     && apt install -y nginx openssl \
#     && mkdir -p /etc/nginx/ssl \
#     && openssl req -newkey rsa:4096 -x509 -sha256 -days 365 -nodes -out /etc/nginx/ssl/maburnet.crt -keyout /etc/nginx/ssl/maburnet.key -subj "/C=FR/ST=IDF/L=Paris/O=42 school/OU=maburnet/CN=maburnet.42.fr/UID=maburnet" \
#     && mkdir -p /var/run/nginx \
#     && chmod 755 /var/www/html \
#     && chown -R www-data:www-data /var/www/html


# COPY /conf/nginx.conf /etc/nginx/conf.d/nginx.conf


# # RUN chown -R nginx:nginx /var/log/nginx /var/cache/nginx
# # RUN chmod 755 /etc/nginx/nginx.conf

# EXPOSE 443

# CMD [ "nginx", "-g", "daemon off;" ]

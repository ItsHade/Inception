FROM debian:bullseye

RUN apt update -y \
    && apt upgrade -y \
    && apt install -y wget curl bash php php-cgi php-mysql php-fpm php-pdo php-gd php-cli php-mbstring redis php-redis \
    && wget https://fr.wordpress.org/wordpress-6.0-fr_FR.tar.gz -P /var/www \
    && cd /var/www && tar -xzf wordpress-6.0-fr_FR.tar.gz && rm wordpress-6.0-fr_FR.tar.gz \
    && chown -R root:root /var/www/wordpress

    
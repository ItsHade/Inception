FROM debian:bullseye

RUN apt update -y && apt upgrade -y && apt install -y mariadb-server mariadb-client

COPY /conf/50-server.cnf /etc/mysql/mariadb.conf.d/50-server.cnf
# COPY ./tools/mariadb.sh /usr/local/bin/

# RUN chmod +x /usr/local/bin/mariadb.sh

# ENTRYPOINT [ "/usr/local/bin/mariadb.sh" ]

# CMD ["mysqld", "--bind-address=0.0.0.0"]

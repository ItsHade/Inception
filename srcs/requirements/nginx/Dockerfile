FROM debian:bullseye

RUN apt update && apt upgrade && apt install -y nginx

CMD ["nginx", "-g", "daemon off;"]
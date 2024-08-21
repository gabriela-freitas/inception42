FROM debian:bullseye

# Install nginx
RUN apt-get update -y && apt-get upgrade -y && apt-get install -y nginx

# Copy the configuration file
COPY ./config/nginx.conf /etc/nginx/nginx.conf

RUN mkdir -p /var/www/html

COPY ./config/index.html /var/www/html/index.html

CMD ["-g", "daemon off;"]

ENTRYPOINT [ "nginx" ]
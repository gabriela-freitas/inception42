
# pull the base image
FROM debian:bullseye

RUN apt-get update && apt-get upgrade -y

# install the required packages
RUN apt-get install -y curl php php7.4-fpm php-mysql mariadb-client netcat

# copy the wordpress configuration script to the root directory in the container
COPY ./config/wordpress.conf /

RUN  chmod +x wordpress.conf

ENTRYPOINT ["./wordpress.conf"]
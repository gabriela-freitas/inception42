FROM debian:bullseye

# Install mariadb
RUN apt-get update -y && apt-get upgrade -y && apt-get install -y mariadb-server

COPY ./config/mariadb.conf /mariadb.conf

#set the permissions
RUN chmod +x /mariadb.conf

EXPOSE 3306

ENTRYPOINT [ "./mariadb.conf" ]
FROM debian:bullseye

# Install mariadb
RUN apt-get update -y && apt-get upgrade -y && apt-get install -y mariadb-server

COPY ./config/mdb-config.sh /mdb-config.sh

#set the permissions
RUN chmod +x /mdb-config.sh

EXPOSE 3306

ENTRYPOINT [ "./mdb-config.sh" ]
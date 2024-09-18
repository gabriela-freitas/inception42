FROM debian:bullseye

# update and upgrade the system
RUN apt-get update && apt-get upgrade -y

# # install the required packages
RUN apt-get install -y nginx openssl

# create the ssl directory
RUN mkdir -p /etc/nginx/ssl

# This command generates a self-signed SSL certificate using OpenSSL.
# In cryptography and computer security, self-signed certificates are public key certificates that are not issued by a certificate authority (CA). 
RUN openssl req -x509 -nodes -out /etc/nginx/ssl/inception.crt -keyout \
    /etc/nginx/ssl/inception.key -subj "/C=PT/ST=Lisbon/L=Lisbon/O=42/OU=42/CN=gafreita.42.fr/UID=gafreita"

# copy the nginx configuration file
COPY ./config/nginx.conf /etc/nginx/nginx.conf

# create the wordpress directory
RUN mkdir -p /var/www/wordpress

# change the owner of the wordpress directory to www-data
RUN chown -R www-data:www-data /var/www/wordpress

# define the command to run when the container starts
CMD ["nginx", "-g", "daemon off;"]
# Ensures that NGINX runs in the foreground, which is necessary for the Docker container to stay alive. 
# If NGINX were to run in the background (daemon mode), the Docker container would exit immediately after NGINX starts.
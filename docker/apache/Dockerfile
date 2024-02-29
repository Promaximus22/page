FROM httpd:2.4

# Update packages and install necessary tools
RUN apt-get update && \
    apt-get install -y nano apache2-utils

# Set the username and password
# ENV USERNAME martin
# ENV PASSWORD matt

# # Create .htpasswd file with the username and password
# RUN echo $USERNAME:$(openssl passwd -apr1 $PASSWORD) > /usr/local/apache2/.htpasswd

# Enable .htaccess
RUN sed -i 's/AllowOverride None/AllowOverride All/g' /usr/local/apache2/conf/httpd.conf

# Copy .htaccess file into the Docker image
COPY ./.htaccess /usr/local/apache2/htdocs/.htaccess
COPY ./.htpasswd /usr/local/apache2/htdocs/.htpasswd

COPY index.html /usr/local/apache2/htdocs/index.html
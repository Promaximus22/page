FROM nginx:alpine

# Install httpd-tools
RUN apk add --no-cache apache2-utils

# Create a password file
RUN htpasswd -cb /etc/nginx/.htpasswd martin matt

# Remove default nginx configuration
RUN rm /etc/nginx/conf.d/default.conf

# Copy the Nginx configuration file
COPY default.conf /etc/nginx/conf.d/
COPY ./site/index.html /usr/share/nginx/html/index.html
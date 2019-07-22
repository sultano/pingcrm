FROM php:7.2-apache

# Install packages
RUN apt-get update && apt-get install -y vim git zip unzip libcurl4-openssl-dev pkg-config libssl-dev gnupg

# Install Node.js
RUN curl -sL https://deb.nodesource.com/setup_10.x | bash - && apt-get install -y nodejs
RUN npm install gulp -g

# Enable Apache modules
RUN a2enmod rewrite

# Configure Apache vhost
RUN sed -i 's/DocumentRoot \/var\/www\/html/DocumentRoot \/var\/www\/html\/public/' /etc/apache2/sites-available/000-default.conf

# Set environemt
ENV PATH /var/www/html/vendor/bin:$PATH

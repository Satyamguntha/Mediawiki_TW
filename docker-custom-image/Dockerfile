#e the official PHP image as the base image
FROM php:7.4-apache

# Install required dependencies
RUN apt-get update && apt-get install -y \
    curl \
    libicu-dev \
    libxml2-dev \
    libonig-dev \ 
    && docker-php-ext-install \
    intl \
    mbstring \
    mysqli \
    xml \
    && a2enmod rewrite

# Download and extract MediaWiki
WORKDIR /var/www/html
RUN curl -O https://releases.wikimedia.org/mediawiki/1.35/mediawiki-1.35.5.tar.gz
RUN tar -xzvf mediawiki-1.35.5.tar.gz --strip-components=1
RUN rm mediawiki-1.35.5.tar.gz

# Expose port 80
EXPOSE 80


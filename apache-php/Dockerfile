FROM php:8.3-apache

# Install necessary PHP extensions and tools
RUN apt-get update && apt-get install -y \
    libfreetype6-dev \
    libjpeg62-turbo-dev \
    libpng-dev \
    libwebp-dev \
    libxpm-dev \
    libzip-dev \
    unzip \
    vim \
    curl \
    && docker-php-ext-configure gd --with-freetype --with-jpeg --with-webp --with-xpm \
    && docker-php-ext-install gd pdo pdo_mysql mysqli

# Enable Apache modules
RUN a2enmod rewrite

# Copy any additional Apache config (optional)
# COPY config/apache2.conf /etc/apache2/apache2.conf

# Expose web root
WORKDIR /var/www/html

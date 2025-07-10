FROM mcr.microsoft.com/devcontainers/php:8.2-apache

# Install system dependencies
RUN apt-get update && \
    apt-get install -y \
    git unzip mariadb-client nodejs npm default-mysql-client && \
    rm -rf /var/lib/apt/lists/*

# Install Composer globally
COPY --from=composer:2 /usr/bin/composer /usr/local/bin/composer

# Enable Apache mod_rewrite
RUN a2enmod rewrite

# Set up DocumentRoot to Drupal web directory
RUN sed -i 's|/var/www/html|/var/www/html/web|g' /etc/apache2/sites-available/000-default.conf

# Set working directory
WORKDIR /var/www/html

# Set permissions
RUN chown -R www-data:www-data /var/www/html
FROM ubuntu:22.04

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && \
    apt-get install -y software-properties-common && \
    add-apt-repository ppa:ondrej/php -y && \
    apt-get update && \
    apt-get install -y \
    apache2=2.4.* \
    php8.3 php8.3-cli php8.3-common php8.3-mysql php8.3-gd php8.3-xml php8.3-mbstring php8.3-curl php8.3-zip php8.3-bcmath php8.3-opcache php8.3-readline php8.3-intl \
    libapache2-mod-php8.3 \
    unzip git curl wget nodejs npm mariadb-client && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

COPY --from=composer:2 /usr/bin/composer /usr/local/bin/composer

RUN a2enmod rewrite
RUN sed -i 's|/var/www/html|/var/www/html/drupal/web|g' /etc/apache2/sites-available/000-default.conf

WORKDIR /var/www/html/drupal
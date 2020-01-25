FROM php:5.6-fpm


#Instal pdo 
RUN docker-php-ext-install pdo pdo_mysql

# Install mysqli 
RUN docker-php-ext-install mysqli && docker-php-ext-enable mysqli

# Install composer
RUN curl -sS https://getcomposer.org/installer | php -- \
        --filename=composer \
        --install-dir=/usr/local/bin && \
        echo "alias composer='composer'" >> /root/.bashrc && \
        composer

COPY public/ /var/www/html/        

WORKDIR "/public"
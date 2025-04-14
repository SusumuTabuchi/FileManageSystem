ARG PHP_VERSION
FROM php:${PHP_VERSION}-fpm

# 拡張機能
RUN apt-get update && apt-get install -y \
    git \
    curl \
    libpq-dev \
    && docker-php-ext-install pdo pdo_pgsql

# Node.js
ARG NODE_VERSION
RUN curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
ENV NVM_DIR=/root/.nvm
RUN . "$NVM_DIR/nvm.sh" && nvm install ${NODE_VERSION}
RUN . "$NVM_DIR/nvm.sh" && nvm use ${NODE_VERSION}
RUN . "$NVM_DIR/nvm.sh" && nvm alias default v${NODE_VERSION}
ENV PATH="/root/.nvm/versions/node/v${NODE_VERSION}/bin/:${PATH}"
RUN node --version
RUN npm --version

# composer
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

WORKDIR /var/www/html/app

EXPOSE 5173

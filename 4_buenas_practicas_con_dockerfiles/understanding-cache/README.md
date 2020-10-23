# Cache in Docker

### Command for create image
```
docker build -t "codely-hello-world" .
```

- Docker create a layer FOR EACH LINE in the Dockerfile.
- When we run docker build, docker checks if the instruction to execute has already done, if it has already done, docker does not execute it again and uses the cache.
- The cache works sequentially, since it finds a point where there was a change, all the following steps will be executed again.

- In this example:
```
FROM php:7.2-apache

COPY index.php /var/www/html/
COPY php.ini /usr/local/etc/php/php.ini

RUN pecl install xdebug-2.6.0 \
    && docker-php-ext-enable xdebug \
    && docker-php-ext-install pdo pdo_mysql

```

- If we make one change in index.php, all the next steps will be executed again, so the trick is to move the steps that change frequently, to the end of the file:

```
FROM php:7.2-apache

RUN pecl install xdebug-2.6.0 \
    && docker-php-ext-enable xdebug \
    && docker-php-ext-install pdo pdo_mysql

COPY php.ini /usr/local/etc/php/php.ini
COPY index.php /var/www/html/
```

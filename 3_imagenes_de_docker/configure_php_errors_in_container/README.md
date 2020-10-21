# Application with error, configure container for errors in PHP

### Command for create image with name "codelytv-hello-world-php-ini"
```
docker build -t "codelytv-hello-world-php-ini" .
```

### Command for create container with this image
```
docker run --rm -p 8000:80 -it "codelytv-hello-world-php-ini"
```

### Command for test container
```
curl -i localhost:8000
```

### Example of Dockerfile installing php depencies (xdebug and pdo_mysql), in file Dockerfile_custom_extension. Command for build this image
```
docker build -t "codelytv-hello-world-php-ini-custom-ext" . -f Dockerfile_custom_extension
```

### Commands for run and test container
```
docker run --rm -p 8000:80 -it "codelytv-hello-world-php-ini-custom-ext"
curl -i localhost:8000
```

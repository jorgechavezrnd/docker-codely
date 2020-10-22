# Example of environment variables
- In Dockerfile, we add one env variable with `ENV DISPLAY_ERRORS="On"`
- This variable is used in php.ini, for configure `display_errors`

### Command for build image
```
docker build -t "codelytv-hello-world-php" .
```

### Command for start container
```
docker run --rm -it -p 8000:80 "codelytv-hello-world-php"
```
- The go to http://localhost:8000

### Command for override env variable
```
docker run --rm -it -e DISPLAY_ERRORS=Off -p 8000:80 "codelytv-hello-world-php"
```

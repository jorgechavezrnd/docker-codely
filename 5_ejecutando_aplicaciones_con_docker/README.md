# Command for build image
```
docker build -t "my-php-application" .
```

- With "EXPOSE" keword in Dockerfile, we can specify the port to expose. This is only a "documentation", we can specify the port in "docker run" command with "-p" flag
```
docker run --rm -it -p 80 my-php-application
```
- In this case, the port 80 of the container will be mapped to a random port of the computer, we can see the port mapped with `docker ps` command

- Or we can use the "-P" flag for map all the ports specified in Dockerfile, and not manually like with "-p" flag
```
docker run --rm -it -P my-php-application
```

- We can specify the port to mapped to with "-p" flag
```
docker run --rm -it -p 8000:80 my-php-application
```

- IMPORTANT: if we want to map a port lower than 1024, we will need to be root

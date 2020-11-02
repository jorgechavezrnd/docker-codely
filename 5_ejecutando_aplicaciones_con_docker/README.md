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

# Restart failed containers automatically
```
docker run -it --restart=always -p 8000:80 my-php-application
```
- This container will execute EVER, if we restart the docker service, the container will start automatically, others values for "--restart" flag: https://docs.docker.com/engine/reference/run/#restart-policies---restart

# limit CPU and memory
```
docker run -it --cpus=1.5 --memory=500m --restart=always -p 8000:80 my-php-application
```
- With "--memory" flag we specify the limit for the memory, if we exceed the limit, the docker servie will kill this container, if we configure the "--restart" flag, the docker service will restart the container, depending of "--restart" value
- With "--cpus" flag we configure the number of CPUs
- With "--cpu-shared" flag we specify the CPU shares (relative weight), this only applies when we have a shortage of CPUs

# Persist data with volumes
```
docker run -it --name vol-test -v codely-volume:/data ubuntu
```

```
docker run -it -p 8000:80 -v $PWD:/var/www/html php:7.2-apache
```
- We create a container for serve the php app, and we can modify the code and view the changes in real time.

- In Dockerfile, we can use the "VOLUME" keword for specify the volume

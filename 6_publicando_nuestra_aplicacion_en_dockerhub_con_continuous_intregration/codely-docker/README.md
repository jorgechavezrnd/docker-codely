# Docker
Material para el curso de CodelyTV Pro [https://pro.codely.tv/library/](https://pro.codely.tv/library/).

# For create repository in docker hup and connect with github for Continuous Integration
- Go to https://hub.docker.com/repositories and connect your docker hub with your github account.
- In this example i used the repository https://github.com/jorgechavezrnd/codely-php-docker-ci-example
- We can see the builds in https://hub.docker.com/repository/docker/jccr2/codely-php-docker-ci-example/builds

- The image will rebuild on any push a new change in master branch

# For run the container
```
docker run --rm -it -p 8000:80 jccr2/codely-php-docker-ci-example
```

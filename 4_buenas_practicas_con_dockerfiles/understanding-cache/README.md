# Cache in Docker

### Command for create image
```
docker build -t "codely-hello-world" .
```

- Docker create a layer FOR EACH LINE in the Dockerfile
- When we run docker build, docker checks if the instruction to execute has already done, if it has already done, docker does not execute it again and uses the cache

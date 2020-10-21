# Dockerfile for PHP Hello World application

### Command for create image with name "codelytv-hello-world"
```
docker build -t "codelytv-hello-world" .
```

### Command for create container with this image
```
docker run --rm -p 8000:80 -it "codelytv-hello-world"
```

### Command for test container
```
curl -i localhost:8000
```

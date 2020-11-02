- Docker compose is a tool that allows us to write to a yaml file, which allows us to specify the applications or containers that we want to start

# Command for start docker containers specified in docker-compose.yaml file
```
docker-compose up
```

# Command for list containers
```
docker-compose ps
```

# Command for show logs of "app" service (The name of the service is "app" in docker-compose.yaml)
```
docker-compose logs -f app
```

# Command like "top" in UNIX
```
docker-compose top
```

# Command for run containers in background
```
docker-compose up -d
```

# Command for stop containers
```
docker-compose stop
```

# Command for stop and delete containers
```
docker-compose down
```

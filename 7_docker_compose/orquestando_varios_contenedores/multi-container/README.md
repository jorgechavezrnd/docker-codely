# Example building multiple containers

- With "depends_on: - mysql", in line 14 of docker-compose.yaml, we specify that the "app" service needs the "mysql" service, so the "app" service won't start until the "mysql" service start

- In "mysql" service, as we use a mysql official image, in the documentation says that all the migrations that we put on "docker-entrypoint-initdb.d", will be executed on start mysql service, so we can use the "database.sql" file in "migrations" folder for initialize the database

- As a third service we will raise a container with "adminer" (a graphical web interface for mysql), in this service we use "depends_on: - mysql" again

# Command for start services or containers
```
docker-compose up
```

# URL for php app
```
http://localhost:8000/
```

# URL for adminer
```
http://localhost:8080/
```

# Credentials for adminer, in "Server" is the service name for mysql container, in this case is "mysql"
- System:   MySQL
- Server:   mysql
- Username: root
- Password: root
- Database: codelytv_pro

# Command for force to try to rebuild the images
```
docker-compose up --build
```

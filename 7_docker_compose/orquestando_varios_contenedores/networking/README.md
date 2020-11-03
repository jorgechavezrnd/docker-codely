# Example of networks with docker compose

# Command for list networks
```
docker network ls
```
# Define networks on each service
- In each service, for example in "app", service, we define a new key, the "network" key, with "network" key we specify which networks we want this service to belong to, in this case, the "app" service only belongs to "codelytv-network" and "application" networks

# Define and create networks
- In line 39 of "docker-compose.yaml" file, we can specify the networks that we want to create

# Command for create network
```
docker network create codelytv-network
```

- In line 40, with this definition:
```
codelytv-network:
    external:
      name: codelytv-network
```
- We specify that we want to connect to one network that was created OUT of this "docker-compose.yaml" file. With "external" we sepecify that this network did not be created by this docker-compose, and with "name" we specify the name of the network that allready exists, the first "codelytv-network" is the name for this network that we want to use in this "docker-compose.yaml" file

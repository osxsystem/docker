## Container Linking

#### Docker Container Linking Options
* Use Legacy Linking
* Add Containers to a bridge Network

#### Linking Containers by Name (legacy linking)
1. Run a Container with a Name.

```
	docker run -d --name my-postgres postgres
```

2. Link to Running Container by Name

![alt text](https://github.com/osxsystem/docker/blob/master/images/linking_containers.png?raw=true "")

3. Repeat for additional containers.

#### Container Networks
1. Create a custom bridge network.

```
	docker network create --driver bridge isolated_network
```
![alt text](https://github.com/osxsystem/docker/blob/master/images/create_cuatom_network.png?raw=true "")

2. Run containers in the network

```
	docker run -d --net=isolated_network --name mongodb mongo
```

![alt text](https://github.com/osxsystem/docker/blob/master/images/run_container_in_network.png?raw=true "")

Example Linking Asp.net and postgres

```
	docker network ls
```

1. create a custom network

```
	docker network create --driver bridge isolated_network
	
	docker network ls
```
2. run container in the network

```
docker run -d --net=isolated_network --name postgres -e POSTGRES_PASSWORD=password postgres

docker run -d --net=isolated_network --name aspnetcoreapp -p 5000:5000 viethung/aspnetcore

docker network inspect <name_of_network>
```
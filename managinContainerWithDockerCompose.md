## Docker Compose
1. Introduce Docker compose
2. The docker-compose.yml file
3. Docker Compose Command
4. Example
5. Setting up Development Environment Services
6. Creating a custom docker-compose.yml file
7. Managin Development Environment services.

#### Introduction
* Docker compose manages your App Lifecycle.
* Start, stop and rebuild services.
* View status of running services
* Stream the log output of running services
* Run one off command on a services.

![alt text](https://github.com/osxsystem/docker/blob/master/images/docker-compose-image.png?raw=true "")

#### The role of the docker-compose file
docker-compose.yml used to build services (Apache, php, mysql,... images) and also used to config services.

![alt text](https://github.com/osxsystem/docker/blob/master/images/dockerComposeYml.png?raw=true "")

![alt text](https://github.com/osxsystem/docker/blob/master/images/config_yml.png?raw=true "")

```yml
version: '2'
services:
	node:
		build:
			context: .
			dockerfile: node.dockerfile
		networks:
			-nodeapp-network
	mongodb:
		image:mongo
		networks:
			-nodeapp-network
	networks:
		nodeapp-network
			driver:bridge
```

#### Docker Command

```
docker-compose build
docker-compose up
docker-compose down
docker-compose log
docker-compose ps
docker-compose stop
docker-compose start
docker-compose rm

```

#### Example
compose nodejs + mongodb
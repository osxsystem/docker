## Building custom images with dockerfile.

#### Get source code into a container
![alt text](https://github.com/osxsystem/docker/blob/master/images/getsourcecodeintocontainer.png?raw=true "")

1. Create a container volume that point to source code.
2. Add your source code into a custom image that is used to create a container.

![alt text](https://github.com/osxsystem/docker/blob/master/images/dockerfiles_build_image.png?raw=true "")

#### Dockerfile
* Text file used to build Docker images. Name it whatever you want.
* Contains build instructions.
* Instructions create intermediate image that can be cached to speed up future builds.
* Used with <code>docker build</code> command.

[Dockerfile reference
](https://docs.docker.com/engine/reference/builder/)

```Dockerfile
	FROM				node:latest
	MAINTAINER        	Do Viet Hung
	COPY				. /var/wwww
	WORKDIR				/var/wwww
	RUN					npm install
	EXPOSE				8080
	ENTRYPOINT			["node", "server.js"]

```

![alt text](https://github.com/osxsystem/docker/blob/master/images/build_image.png?raw=true "")
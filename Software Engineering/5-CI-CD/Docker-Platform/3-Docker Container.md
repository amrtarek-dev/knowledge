# What is the Docker Container and how to run it?
When a Docker image is run, it creates a Docker container, which is a running instance of the image. Multiple containers can be created from the same image, each with its own isolated environment and resources, making it easy to run multiple instances of an application on the same machine.

A container is an isolated place where an application runs without affecting the rest of the system and without the system impacting the application. Therefore containers are well-suited for securely running software like databases or web applications that need access to sensitive resources without giving access to every user on the system.

## State

Docker containers have six states which represent a piece of valuable information about the container:

1. Created
2. Running
3. Restarting
4. Paused
5. Exited
6. Dead

### Create
Docker assign the *Create* stater for containers when it is just created and never started

> Hence, no CPU or memory is used by the containers in this state.

So it will be after creating a container from the docker image by running

```bash
docker create <image tag>
docker container ls -a
```
the first command will create a container, and the second will list the container with the state *Created*.

### Running
You can run a container that is already created or exited by running

```bash
docker start <container name>
```

And you can join an already running container by the **attach** command

```bash
docker attach <container name>
```

### Restarting
This is a state for the container when it is restarting, you can achieve this state when you restart a container by

```bash
docker restart <container name>
```

### Paused

You can pause an already-running container

> Hence, The paused container reserves the same memory but it is not consuming CPU

```bash
docker pause <container name>
```

### Exited
This state can occur in two cases:
1. if the container has been stopped by the docker 
   
   ```bash
   docker stop <container name>
   ```

2. There is an exception happened in the container or the process execution inside the container has been done.

### Dead
The dead state of a Docker container means that the container is non-functioning. This state is achieved when we try to remove the container, but it cannot be removed because some resources are still in use by an external process. Hence, the container is moved to the dead state.

> Containers in a dead state cannot be restarted. and they do not consume any memory or CPU. 

## Generate Container
To generate a container to work with Docker has pre-steps to do so:

1. You have to have an Image
2. Run the image to have a container from it (you can consider it as an instance of the image)

We will assume here that you already have an Image generated container from it, and we will discuss the image creation in the next topic, but for now, assume that we have a docker image.

## List image

so we can list the docker images by:

```bash
docker image ls
```

## Create a container

then create a container from the image

```bash
docker create <image tag>
```

## List containers

After this command, you will have a new container, and you can list the containers by

```bash
docker container ls -a
```

this command will list all containers (the running and the stopped containers), and list only the running containers

```bash
docker container ls
```

## Start container

To start an ideal container 

```bash
docker run <container name>
```

### To join to a running container

```bash
docker attach <container name>
```

### To get stdin, stdout and tty with container

```bash
docker run -i -t <container name>
```

### To share folder between the host and the container

```bash
docker run -v <host dir>:<container dir>
```

### To install or run command in container

```bash
docker exec -it [container] pip3 install pandas
```
this will install pandas for python3 for example.


## Stop container

To stop already running container

```bash
docker stop <container name>
```

Now you have enough information to understand the docker container, we will cover more container commands and specs in the next topics, so see you around

## Delete containers
To delete container
```shell
docker rm <container name>
```

To delete all containers
```shell
docker rm $(docker ps -a -q)
```

## Containers inspect
Get information about the container
```shell
docker inspect <container name>
```
To get the container IP for example
```shell
docker inspect <container id> | grep "IPAddress"
```

## Containers exec
To run command in running container
```shell
docker exec <container name> <command>
```
To access the docker container
```shell
docker exec -it <conatiner name> /bin/bash
```

## Containers Rename
To rename container
``` bash
docker rename <old-container-name> <new-container-name>
```

## Create Image from Container
To make an image from existed container
``` bash
docker commit <container_name> <image_name>
```

## Add volume to container
To make a shared volume between the host and docker image
``` bash
docker run -dit --name <new-container-name> -v <host-path>:<container-path> <image-name>
```

## Git logs of the container
To get the latest logs of the running container
``` bash
docker logs <container-name>
```
You can limit the logs for specific lines by `-n` and the number of lines, or `--tail`
``` bash
docker logs -n 10 <container-name>
```
You can keep track the logs by `-f, --follow`
``` bash
docker logs -n 10 -f <container-name>
```
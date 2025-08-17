A Docker image is a lightweight, standalone, and executable package that contains everything needed to run a piece of software, including the code, libraries, dependencies, and system tools. It is built from a Dockerfile, which is a script that specifies the instructions to create the image.

Docker images are designed to be portable and platform-independent, which means they can run on any machine that has Docker installed, regardless of the underlying operating system or hardware. They are also easy to share, distribute, and deploy, making them a popular choice for developers, DevOps teams, and system administrators.

## Docker Images

Images are like the blueprint for containers, like the class in OOP, and the container is the object.

- It has its own root file system
- It is read only so once it is created you can not edit it.
- Containers are the running instance of an image that runs our application.

Images are made up from several layers:

- **Parent image**: Includes the OS & sometimes the runtime environment.
- **Source code**
- **Dependencies**

| Image        |
|:------------:|
| Run commands |
| Dependencies |
| Source code  |
| Parent image |

> **Parent image** is the docker image that normally could be cloned from docker-hub by the specific tag or latest tag.

To make a docker image you have to write a **Dockerfile** to describe this image.

## DockerFile

A Dockerfile is a text file that contains a set of instructions for building a Docker image. It specifies the base image to use, the files to add to the image, the commands to run during the build process, and other configuration settings.

A typical Dockerfile includes a set of instructions that follow a specific format, including:

- The base image to use (e.g., Ubuntu, Alpine, etc.)
- Any additional packages or dependencies to install
- The files to add to the image, either by copying them from the host machine or downloading them from a remote source
- Any configuration settings or environment variables to set
- Any commands to run during the build process, such as building the application or setting up the runtime environment
- Any commands to run when the container is started, such as starting the application server or running tests.

Once the Dockerfile is created, it can be used to build a Docker image by running the **"docker build"** command. This command reads the instructions in the Dockerfile and creates a new image that can be run as a Docker container. The resulting image is portable and can be run on any machine with Docker installed.

In short, the Dockerfile method is a three-step process whereby you create the Dockerfile and add the commands you need to assemble the image.

### Example Dockerfile

This DockerFile will build an image with **Ubuntu 18.04** and it has **curl** and **Nginx** already installed.

```bash
# Use the official Ubuntu 18.04 as base
FROM ubuntu:18.04
# Install Nginx and curl
RUN apt-get update &&
apt-get upgrade -y &&
apt-get install -y nginx curl &&
rm -rf /var/lib/apt/lists/*
```

After saving this code in file named **Dockerfile** you can Build an image from this file by running 

```bash
docker build .
```

Or by using the **-t** flag to add a name to the generated image

```bash
# docker build -t <tag> <path for Dockerfile>
docker build . -t nginx:1.0
```

where nginx is the image name, and 1.0 is the version.

### List images

To check and list the docker images you can use 

```bash
docker image ls
```

or

```bash
docker images
```

the Output should be something like this

```bash
$ docker images

REPOSITORY     TAG      IMAGE ID        CREATED SIZE

nginx           0.1     f95ae2e1344b    10 seconds ago 138MB

ubuntu         18.04    ccc6e87d482b    12 days ago 64.2MB
```

let's see some of the **Dockerfile** commands that we can use to build the **Dockerfile**.

### Remove images
To remove a docker image

```bash
docker image rm <IMAGE ID>
```

To clear all images and containers that is not used.

```bash
docker system prune -a
# To clear the build cache
docker builder prune
# To remove the dangling images
docker rmi $(docker images -f "dangling=true" -q)
```

### DockerFile Commands

The following table shows you those Dockerfile statements you’re most likely to use:

| Command | Meaning                                                                                | Example                  |
|:-------:|:-------------------------------------------------------------------------------------- | ------------------------ |
| FROM    | To specify the parent image.                                                           | FROM node:17-alpine      |
| WORKDIR | To set the working directory for any commands that follow in the Dockerfile.           | WORKDIR /app             |
| RUN     | To install any applications and packages required for your container before initiation | RUN npm install          |
| CMD     | To run command on the container after initiation                                       | CMD ["python","main.py"] |
| COPY    | To copy over files or directories from a specific location.                            | COPY <src> <dis>         |
|  ADD          |  As COPY, but also able to handle remote URLs and unpack compressed files.  |  ADD <src> <dis>          |
|  EXPOSE  | To make a port mapping for the container you have to expose the port                   |  EXPOSE <port number>     |

> Each line in the docker file is a layer in our image, so it is recommended to reduce the commands used to reduce the memory that is used by the image.

So now we are ready to run the image and create a container to work with.
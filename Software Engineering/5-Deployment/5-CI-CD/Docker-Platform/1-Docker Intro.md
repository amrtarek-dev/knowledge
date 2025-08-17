Docker is a container management tool that allows users to create independent and isolated environments in which to launch and deploy their applications. These environments are then referred to as containers. It has a command prompt version that you can use from the command line, as well as a Graphical Interface that allows you to manage images and containers through a Windows interface. The developer can now run a container on any machine.

As you can see, with Docker, there are no more dependency or compilation problems. All you have to do is launch your container and your application will launch immediately.

To understand Docker you have to understand multiple points:
- What is the DockerFile
- What is the Docker image
- What is the Docker Container


## VM vs Docker
There is a significant difference between Virtual machines and Containers:
- VMs make their own hardware emulator which can be configured to use apart from the physical hardware of the machine, but the docker container shares the machine's hardware, making it faster.
- VMs has to install their own Operating system to work in an isolated flavour, but Docker image can share the host OS ex: Linux containers on Linux Host is using the host kernel, which makes it faster to deploy and run.

## Why use Docker as a developer?
This tool can really change a developer’s daily life because:
- Docker is fast. Unlike a virtual machine, your application can start in a few seconds and stop just as quickly.
- Docker is multi-platform. You can launch your container on any system.
- Containers can be built and destroyed faster than a virtual machine.
- No more difficulties setting up your working environment. Once your Docker is configured, you will never have to reinstall your dependencies manually again. If you change computers or if an employee joins your company, you only have to give them your configuration.
- You keep your work space clean, as each of your environments will be isolated and you can delete them anytime without impacting the rest.
It will be easier to deploy your project on your server to put it online.

## Docker elements
Docker has main elements:
1. Docker file
2. Docker image
3. Docker container

The build sequence for Docker is :
Make a **Docker file**, then Build the Docker file to make a **Docker image**, and then run the Docker image to make a **Docker container**.

## Install Docker
- For Windows, you can follow the download and install instructions on the official website [Install Docker for Windows](https://docs.docker.com/desktop/install/windows-install/)
- For Ubuntu, you can run this command
```bash
sudo apt install docker.io
```
Once the installation is finished, you can test your Docker by running this command in the command line
```bash
docker -v
```
The result will be the docker version, if not then the docker did not install correctly, and you have to install it again.


So now your environment is ready, so let's understand more about the Docker file and Docker Images.
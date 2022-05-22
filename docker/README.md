# Using Docker (https://d1.awsstatic.com/acs/characters/Logos/Docker-Logo_Horizontel_279x131.b8a5c41e56b77706656d61080f6a0217a3ba356d.png) 
Docker is a set of platform as a service (PaaS) products that use OS-level virtualization to deliver software in packages called containers.Containers are isolated from one another and bundle their own software, libraries and configuration files; they can communicate with each other through well-defined channels. Because all of the containers share the services of a single operating system kernel, they use fewer resources than virtual machines.

This is a simple Docker lab that builds and prepares an HTML page for display.

## Prerequisites
- Working knowledge of Linux CLI.
- Docker CLI installed.
- Basic git knowledge.

## How-to
Make sure you're in this directory. Run ls and make sure 'page.html' and 'Dockerfile' are present. The Dockerfile runs on `bullseye-slim` and build httpd ver. 2.4.53. This is the latest build as of present. Line 235 in Dockerfile copies page.html to the container's html directory. The page is a weather widget for Oakland, CA. Feel free to edit page.html however you want.

The Dockerfile installs a number of packages and dependencies, opens port 80 in the container, and starts the apache web server process in the foreground. Edit the docker file however you'd like to build upon the image.

Once the container is running, open your internet browser and enter 'http://localhost:8080'. That's where the webpage will be running.

### Building the image
```bash
docker build -t <repo name>:<tag name> .
```
### Verify images
```bash
docker images
```
Docker will return all images. Copy the Image ID of the image you just built.
### Run container with built image
```bash
docker run -d -p 8080:80 <Image ID>
```
This runs a container with the image listening on port 8080. Port 80 is set based on the Dockerfile 'EXPOSE' port 80.  
### Common Docker commands
```bash
docker images # List docker images 
docker container ls # List RUNNING docker containers
docker container ls -a # List ALL docker containers
docker container stop
docker exec -it <Container ID> /bin/bash # Access running container via bash shell.
docker container rm <Container ID> # Delete docker container. Container must be stopped.
docker rmi <Image ID> # Delete image. Image must not be present on any existing docker containers. If so, the containers must be deleted before deleting the image.
```

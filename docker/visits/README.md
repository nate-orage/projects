<!-- ![](https://upload.wikimedia.org/wikipedia/commons/thumb/7/7e/Node.js_logo_2015.svg/2560px-Node.js_logo_2015.svg.png) ![](https://d1.awsstatic.com/acs/characters/Logos/Docker-Logo_Horizontel_279x131.b8a5c41e56b77706656d61080f6a0217a3ba356d.png) ![](https://upload.wikimedia.org/wikipedia/en/6/6b/Redis_Logo.svg) -->
# Visitor Counter - Node.js and Redis container
## Purpose
Docker container to deploy a visitor counter.
## Commands
```bash
# Build the container
docker-compose build
# Run the container
docker-compose up
# Build the container and run it in the backgroud
docker-compose up --build -d
```
## Common Docker commands
```bash
docker images # List docker images 
docker container ls # List RUNNING docker containers
docker container ls -a # List ALL docker containers
docker container stop
docker exec -it <Container ID> /bin/bash # Access running container via bash shell.
docker container rm <Container ID> # Delete docker container. Container must be stopped.
docker rmi <Image ID> # Delete image. Image must not be present on any existing docker containers. If so, the containers must be deleted before deleting the image.
```
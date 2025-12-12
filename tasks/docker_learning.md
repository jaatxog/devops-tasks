Docker – Major Commands and Use Cases
====================================

This document lists commonly used Docker commands along with their practical
use cases. It is intended for quick reference, interview preparation, and
day-to-day DevOps operations.

--------------------------------------------------
Docker Installation and Service Management
--------------------------------------------------

Command:
yum install -y docker-ce docker-ce-cli containerd.io

Use Case:
Installs Docker Engine, Docker CLI, and the container runtime on RHEL/AlmaLinux
based systems.

Command:
systemctl start docker

Use Case:
Starts the Docker service so containers can be created and run.

Command:
systemctl enable docker

Use Case:
Ensures Docker starts automatically after a system reboot.

--------------------------------------------------
Docker Image Management
--------------------------------------------------

Command:
docker pull nginx:alpine

Use Case:
Downloads the specified image from Docker Hub to the local system.

Command:
docker images

Use Case:
Lists all Docker images available locally.

Command:
docker tag busybox:musl busybox:media

Use Case:
Creates a new tag for an existing image without duplicating the image data.

--------------------------------------------------
Docker Container Management
--------------------------------------------------

Command:
docker run -d --name web -p 8080:80 nginx

Use Case:
Creates and starts a container in detached mode, assigns a name, and maps a
host port to a container port.

Command:
docker ps

Use Case:
Displays all currently running containers.

Command:
docker ps -a

Use Case:
Displays all containers, including running and stopped ones.

Command:
docker stop web

Use Case:
Gracefully stops a running container.

Command:
docker rm web

Use Case:
Removes a stopped container from the system.

--------------------------------------------------
Executing Commands Inside Containers
--------------------------------------------------

Command:
docker exec -it ubuntu_latest bash

Use Case:
Provides interactive shell access inside a running container.

--------------------------------------------------
Copying Files Between Host and Container
--------------------------------------------------

Command:
docker cp /tmp/file.txt container_name:/opt/

Use Case:
Copies a file from the Docker host into a running container without modifying
its contents.

Command:
docker cp container_name:/opt/file.txt .

Use Case:
Copies a file from a container back to the Docker host.

--------------------------------------------------
Creating Images from Running Containers
--------------------------------------------------

Command:
docker commit ubuntu_latest custom:image

Use Case:
Creates a new Docker image from the current state of a running container. Useful
for backing up changes or debugging.

--------------------------------------------------
Docker Networking
--------------------------------------------------

Command:
docker network create mynetwork

Use Case:
Creates an isolated Docker network for container communication.

Command:
docker network inspect mynetwork

Use Case:
Displays detailed configuration of the Docker network and attached containers.

--------------------------------------------------
Docker Volumes
--------------------------------------------------

Command:
docker volume create appdata

Use Case:
Creates a persistent Docker volume for storing application data.

Command:
docker volume ls

Use Case:
Lists all Docker volumes present on the system.

--------------------------------------------------
Docker Compose
--------------------------------------------------

Command:
docker compose up -d

Use Case:
Starts all services defined in a docker-compose.yml file in detached mode.

Command:
docker compose down

Use Case:
Stops and removes containers, networks, and resources created by Docker Compose.

--------------------------------------------------
Docker Image Build and Cleanup
--------------------------------------------------

Command:
docker build -t myimage .

Use Case:
Builds a Docker image using instructions defined in a Dockerfile.

Command:
docker system prune

Use Case:
Removes unused containers, images, networks, and frees disk space.

--------------------------------------------------
Outcome
--------------------------------------------------

This file provides a consolidated list of essential Docker commands and their
real-world use cases. It can be used as a quick reference guide for DevOps
engineers, system administrators, students, and interview preparation.


Add Docker official repository:

yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo


Adds Docker CE repository so Docker packages can be installed.

Install Docker and Docker Compose:

yum install -y docker-ce docker-ce-cli containerd.io docker-compose-plugin


Installs Docker engine, CLI tools, container runtime, and Docker Compose plugin.

Start Docker service:

systemctl start docker


Starts the Docker daemon.

Enable Docker at boot:

systemctl enable docker


Ensures Docker starts automatically after reboot.

Docker Image Management

Pull an image from Docker Hub:

docker pull nginx:alpine-perl


Downloads the specified image and tag from Docker Hub.

List all Docker images:

docker images


Displays all images available locally.

Tag an existing image:

docker tag busybox:musl busybox:media


Creates a new tag pointing to the same image ID.

Docker Container Management

Run a container:

docker run -d --name apps -p 8083:80 nginx:alpine-perl


-d runs container in background

--name assigns a fixed container name

-p maps host port to container port

List running containers:

docker ps


Shows currently running containers.

List all containers (including stopped):

docker ps -a


Displays running and stopped containers.

Execute a command inside a running container:

docker exec -it ubuntu_latest bash


Provides interactive shell access to a running container.

Copy Files Between Host and Container

Copy file from host to container:

docker cp /tmp/nautilus.txt.gpg ubuntu_latest:/opt/


Copies a file without modifying its contents.

Create Image from Running Container

Commit container changes to a new image:

docker commit ubuntu_latest news:datacenter


Creates a new Docker image from the current state of a container.

Docker Networking

Create a custom bridge network:

docker network create \
--driver bridge \
--subnet 172.168.0.0/24 \
--ip-range 172.168.0.0/24 \
news


Creates an isolated Docker bridge network with custom IP addressing.

Inspect a Docker network:

docker network inspect news


Displays network configuration and connected containers.

Docker Compose Usage

Start services defined in docker-compose.yml:

docker compose up -d


Builds and starts all services in detached mode.

Stop and remove compose services:

docker compose down


Stops containers and removes associated resources.

Dockerfile & Image Build

Build an image from Dockerfile:

docker build -t nautilus/python-app .


Creates a Docker image using instructions from Dockerfile.

Common Docker Troubleshooting Commands

Check Docker version:

docker --version


Verifies Docker installation.

Check Docker Compose version:

docker compose version


Verifies Docker Compose availability.

Fix permission issue while creating files:

sudo tee Dockerfile > /dev/null


Used when shell redirection fails with permission denied.

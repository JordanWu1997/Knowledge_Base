# Docker

- Reference
    - https://docs.docker.com/
    - https://docs.docker.com/engine/reference/commandline/run/
    - https://www.youtube.com/watch?v=mPquwpxyUQU
    - https://docs.docker.com/engine/install/fedora/
    - https://www.youtube.com/watch?v=L1ie8negCjc
    - https://hub.docker.com/
    - https://docs.docker.com/engine/install/fedora/
    - https://joshhu.gitbooks.io/docker_theory_install/content/DockerBible/dockerdockertools.html
    - https://ithelp.ithome.com.tw/users/20103456/ironman/1320?page=3
    - https://en.wikipedia.org/wiki/Docker_(software)

# Context

## Docker Introduction

### What can docker do for you
- Create test environment fast and easily
- Provide isolation for environments

### Compare Docker to Virtual Machine (VM)
- Virtual Machine (VM)
    - Need an operating system (OS) to connect to physical hardware
    - Full isolation of hardware resources
- Docker
    - Use host OS as docker engine and use host kernel as well
        - This is why docker is much faster and has smaller storage size
    - Isolation is provided by containers in application level

### Docker Techniques in kernel level
- Namespace: Process environment manager
    - e.g. Process ID, User ID, network and etc.
    - This provides isolation of processes in different environments
- Control Group (Cgroup): System resource management
    - e.g. CPU, RAM, I/O and etc.
    - This provides isolation of system resources in different environments

### Docker Terminology
- __Image__: ~ Snapshot of virtual machine
- __Container__: ~ Virtual machine
- __Dockerfile__: Automation script

## Docker installation on Fedora 36
- Get docker packages
    ```
    sudo dnf -y install dnf-plugins-core
    sudo dnf config-manager --add-repo https://download.docker.com/linux/fedora/docker-ce.repo
    sudo dnf install docker-ce docker-ce-cli containerd.io docker-compose-plugins
    ```
- Start docker service on local host
    ```
    sudo systemctl start docker
    ```
- Test docker service with hello-world test docker
    ```
    sudo docker run hello-world
    ```
- Docker files and engine store in `/var/lib/docker/`

## Dockerfile
Scripts to automate create container and its setup

- Command must be executed within directory where stores docker-compose YAML file
- Build container
    - `docker build -t NAME . --no-cache`

## Basic Usage

### Image
- Search images on Dockerhub (https://hub.docker.com/)
    - `docker search -f is-official=true`
        - `-f is-official=true`: f for filter, restricted search to official images
- Get image from Dockerhub
- `docker pull IMAGE:TAG`
- List local images
    - `docker images`
- Remove downloaded image IMAGE
    - `docker image rm IMAGE`

### Container
- Run container CONTAINER using image IMAGE
    - `docker run -d -t --name CONTAINER IMAGE`
    - `docker run` flags
        - `-d`: detach (will not send message to foreground)
        - `-t`: allocate a pseudo-tty
        - `-p HOST:CONTAINER`: port forwarding host:container
        - `--rm`: automatically remove container when it exits
        - `--env ENV=VALUE`: assign environment variable to container
        - `--restart always`: always restart container
- Run container CONTAINER with image IMAGE and port forwarding to local host
    - `docker run -t -d -p HOST:CONTAINER --name container IMAGE`
- Start container CONTAINER
    - `docker start CONTAINER`
- Stop running container CONTAINER
    - `docker stop container`
- Remove container CONTAINER
    - `docker rm CONTAINER`
- List all containers
    - `docker ps -a`
- List running containers
    - `docker ps`
- Interact with running container CONTAINER with shell SHELL
    - `docker exec -i -t CONTAINER SHELL`
        - `-i`: interactive shell (shell must be packed with image)
- Monitor container resource usage
    - `docker stats`

## Network
- List container network
    - `docker network ls`
- Inspect containers using network NETWORK
    - `docker inspect NETWORK`
- Run container with network NETWORK (e.g. bridge, host)
    - `docker run -i -t --network NETWORK --name CONTAINER IMAGE`

### none
No network connection

- This network is pre-created by docker

### bridge
Container default network is bridge, which generates interface for each container

- Docker use NAT to access external internet, if external network wants visit container, port forwarding is needed
- Create user-defined bridge network NETWORK
    - User-defined bridge network provides network isolation in docker
    - `docker network create NETWORK`

### host
Container uses same network configuration as local host

- No port-forwarding is needed for external network visiting, also means you are exposed to whole external network
- This network is pre-created by docker

### macvlan (bridge)
Container is directly connected to network interface with MAC address

- Problems
    - 2 MAC addresses on 1 port problem, to solve it, `promisc` mode of interface must be turned on
        - `ip link set INTERFACE promisc on`: turn on promisc mode of INTERFACE
    - No DHCP control,
        - If you don't assign IP by yourself, docker will assign one for you with its own DHCP
        - This means you have 2 DHCP service in same network and this might cause IP conflicts to other devices
- Create macvlan network NETWORK in bridge mode
    - `docker network create -d macvlan --subnet IP/MASK --gateway GATEWAY -o parent=INTERFACE NETWORK`
        - `-d`: driver
- Run container with macvlan NETWORK, note that container IP must be assigned and not not used by other devices
    - `docker run -i -t --network NETWORK --ip IP --name CONTAINER IMAGE`

### macvlan (802.1q)
Docker creates sub interfaces and containers are directly connected to sub interfaces

- Create macvlan network NETWORK in 802.1q mode
    - `docker network create -d macvlan --subnet IP/MASK --gateway GATEWAY -o parent=INTERFACE.SUB NETWORK `
- Run container with macvlan NETWORK, note that container IP must be assigned and not not used by other devices
    - `docker run -i -t --network NETWORK --ip IP --name CONTAINER IMAGE`

### ipvlan (L2)
Containers use the same MAC address but difference IP addresses, no more promisc problem, can directly access to external network

- Create ipvlan (L2) network NETWORK
    - `docker network create -d ipvlan --subnet IP/MASK --gateway GATEWAY -o parent=INTERFACE NETWORK`
- Run container with ipvlan (L2) NETWORK, note that container IP must be assigned and not not used by other devices
    - `docker run -i -t --network NETWORK --ip IP --name CONTAINER IMAGE`

### ipvlan (L3)
Containers use host as router and parent interface and they can connect to each other

- Problems
    - No external network access or visiting from external network, to solve it, static route is needed
- Create ipvlan (L3) network NETWORK
    - `docker network create -d ipvlan --subnet IP/MASK -o parent=INTERFACE -o ipvlan_mode=l3 NETWORK`
        - No need to assign gateway

### overlay
Containers connect to each other on different real machine

- e.g.
    - Docker swarm
    - Kubernetes

## Volume
Map container volume to make it persisting or be able to share with other containers
- Map container volume CONTAINER to host volume HOST
    - Add `-v CONTAINER:HOST` to `docker run`
- Share volumes from CONTAINER between containers
    - Add `--volumes-from CONTAINER` to `docker run`

## Hardware Resource
Control hardware resources that container can use
- Restrict container memory size to 512 MB
    - Add `-m 512m` to `docker run`

## Docker-compose
Manage multiple docker containers with `docker-compose.yaml` file

- `docker-compose` command must be executed within directory where stores docker-compose YAML file
- Show container created by docker-compose
    - `docker-compose ps`
- Run docker-compose
    - `docker-compose up -d`
- Stop containers created by docker-compose
    - `docker-compose stop`
- Shutdown and remove containers created by docker-compose
    - `docker-compose down`

## Kubernetes

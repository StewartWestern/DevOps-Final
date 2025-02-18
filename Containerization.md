# Containerization
To add the offical docker repository and install Docker on Linux
```
sudo dnf config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo

sudo dnf install -y docker-ce docker-ce-cli containerd.io docker-compose-plugin
```
Start and enable
```
sudo systemctl start docker
sudo systemctl enable docker
```
Allow non-root user access to avoid having to sudo each time
```
sudo usermod -aG docker $USER
```
Verify Installation
```
docker --version
```
## Basic Docker Commands
to download and run an image 
```
docker pull {image name} 
docker run -d -p 8080:80 {image name}
```
to verify and image is running
```
docker ps
docker ps -a
```
To stop and remove the container use
```
docker stop {image ID}
docker rm {image ID}
```
## Docker Storage
Temporary storage - storage that is inside the container

Volumes - storage that is self contained and can be connected to a container

To create a volume
```
docker volume create {volume name}
```
To attach to a container
```
docker run -id v {volume name}:/data --name {attached name} ubuntu
```
To access the container and run commands in it
```
docker exec -it {container name/ID} bash
```
## Networking
These are some basic networking commands
```
docker network ls
docker netowrk create {bridge name}
docker run -id --network {bridge name} --name {container name} ubuntu
docker network connect {network name} {container name}
```

## Docker Port Mapping
The ```p``` flag is used to map a host port to a container port in the format.
```-p 8080:80``` maps port 80 in the container to port 8080.

for example
```
docker run -d -p 8080:80 nginx
```
## Pre-Built Images
```
docker pull {image name}
docker run -d {any other flags} --name {container-name} {image name}
```
For example this following command will
1. map the ports to container port 8000 to host port 8000
2. map container port 9443 to host port 9443
3. names the container "portainer"
4. maps two volumes to the container /var/run/docker.sock and /var/run/docker.sock
```
docker run --name portainer -p 8000:8000 -p 9443:9443 -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data -d portainer/portainer-ce
```
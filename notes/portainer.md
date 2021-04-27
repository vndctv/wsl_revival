# Portainer Install Notes

## Pre-Installation Commands
- `sudo mkdir -p /data/portainer`

## Portainer Server Install Commands
VM: dev
1.  `docker volume create portainer_data`
2. `docker run -d -p 8000:8000 -p 9000:9000 --name=portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data/portainer portainer/portainer-ce`


## Pertainer Agent Install Command
VM: production


`docker run -d -p 9001:9001 --name portainer_agent --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v /var/lib/docker/volumes:/var/lib/docker/volumes portainer/agent`

## Web Accessable Ports
Server (dev vm): `8000,9000`
Agent (production vm): `9001` 
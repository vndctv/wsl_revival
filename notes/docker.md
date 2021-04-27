# Docker Installation Notes

## Pre-Installation Package Requirements
- `apt-transport-https`
- `ca-certificates`
- `curl`
- `gnupg`
- `lsb-release`

Install with `apt-get` as per usual.

## Installation
The following commands will install Docker on the server.

1. Save Docker GPG: `curl -fsSL https://download.docker.com/linux/debian/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg`
2. Add repositories:
```
echo \
  "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/debian \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null`
```
3. Update package list and install: `sudo apt update && sudo apt-get install docker-ce docker-ce-cli containerd.io`

## Post-Installation
1. Add users to Docker group: `sudo usermod -aG cweber`
2. Start Docker on boot: `sudo systemctl enable docker.service && sudo systemctl enable containerd.service`

## References
- https://docs.docker.com/engine/install/debian/
- https://docs.docker.com/engine/install/linux-postinstall/

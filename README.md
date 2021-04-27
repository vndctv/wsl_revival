# WSL Revival
https://cruisewsl.com

## Essential Services
- SSH (Completed)
- HTTP/S (Completed)
- Database (Completed)
- FTP/SFTP
- [Docker](notes/docker.md) (Completed)
- [Portainer](notes/portainer.md) (Completed)

## Host Operating System
- Debian 10

## Web-Accessible Ports
- 22/TCP
- 80/TCP
- 443/TCP
- 9001/TCP

## nginx Reverse Proxy
`nginx` will act as a reverse proxy to serve `Docker`ized web
apps and other services.

## Database
`mariadb` is our choice of database.

## Security
- [fail2ban](notes/fail2ban.md) (Completed)
- ClamAV (Completed)
- iptables
- Snort

## Infrastructure
2 Virtual Machines:

1. www (production) - Production VM
2. dev (development) - Development VM

## Extras
- [Matomo](https://matomo.org/) for web analytic data

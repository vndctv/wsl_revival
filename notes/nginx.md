# nginx Install Notes
Team WSL will use `nginx` as a reverse proxy to serve
web apps and pages.

## Installation
Installation is straight-forward: `sudo apt install nginx`

## SSL Certificates with Certbot
`Certbot` is installed via `snap`:
```
sudo snap install core ; sudo snap refresh core
sudo snap install --classic certbot
sudo ln -s /snap/bin/certbot /usr/bin/certbot # symlink binary
```

Certificates can then be issued using the command `sudo certbot --nginx`. This will scan the `nginx` configuration files for valid
servers and prompt accordingly.

Configuration file is available here: (confs/www.cruisewsl.com.conf)[../confs/www.cruisewsl.com.conf]
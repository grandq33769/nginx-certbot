# Automatic updated SSL Certificate
## Pre-requisites
* 80 port is accessible

## Procedures
1. Set `server name` in `data/nginx/app.conf`
2. Edit `domains` and `email` in `init-letsencrypt.sh` (Same as 1.)
3. `sudo chmod +x init-letsencrypt.sh`
4. `sudo ./init-letsencrypt.sh`
5. `sudo docker-compose up -d`
6. `sudo chmod 755 data/archive`
7. `sudo chmod 664 data/certbot/conf/live/<domain_name>/privkey.pem`

## Result
cert: `data/certbot/conf/live/<domain_name>/fullchain.pem`
key: `data/certbot/conf/live/<domain_name>/privkey.pem`

## Usage Remarks
Mount the whole directory (`nginx-certbot/data/certbot/`)
like: `nginx-certbot/data/certbot/:/etc/certbot` (in docker-compose)

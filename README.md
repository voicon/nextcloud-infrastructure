# Nextcloud Infrastructure Setup for Synology
This is my Nextcloud infrastructure setup. I am pulling my Nextcloud Docker image from https://github.com/aashish108/nextcloud and is the full Apache version.

## Platform
I created this repo so I could get Nextcloud to work on my Synology NAS server.

# Technologies Used
I have also made use of these technologies:

- MariaDB for the dababase
- PHPMyAdmin to manage the DB
- Portainer to manage the Docker containers
- Nextcloud Apache image
- Redis for a type of caching
- Traefik for the reverse proxy management

# Notes
I have used GoDaddy API for Traefik to arrange for the Letsencrypt SSL certificates.

# Getting Started
## Prerequisites
- Synology server with root & shell access
- Access to your home router so we can control port redirects
- A domain name that is pointing to your Synology NAS
- Docker installed on Synology
- GoDaddy API access (for this guide though alternatives are available)
## Environment Variables for configuring
At the root of the project, you would need a file with the name `.env` with these values:

```
ACME_EMAIL=
DOCKER_URL=
GODADDY_API_KEY=
GODADDY_API_SECRET=
DB_USER=
DB_PASSWORD=
DB_NAME=
MYSQL_URL=
NEXTCLOUD_URL=
```
## Steps
1. git clone this repo and copy the code over to your Synology
1. SSH into that directory
1. Run `sudo docker-compose up -d`, note that sudo is required for Synology NAS
1. That should be it for the Docker side
1. Make sure you port forward port 8282 on your router

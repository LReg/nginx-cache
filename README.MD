# Nginx Cache Server
This is a simple Nginx cache server that caches the responses from the backend server.
It just uses the Nginx docker image and some Environment variables to configure it.
You can configure it via the .env file.
## Pre-requisites
- Docker
## How to run
1. Clone the repository
2. Run `cp .env.example .env`
3. Edit the .env file
4. Run `docker compose up -d`
## How to configure
You can configure the cache server via the .env file.
### Traefik
These are helpful if you are using Traefik as a reverse proxy.
But if not you can just ignore these.
If you want to use traefik use `docker compose -f traefik.docker-compose.yml up -d` to start the container.
- `TRAEFIK_CERT_RESOLVER`  The name of the cert resolver
- `TRAEFIK_ENTRYPOINT` The entrypoint of Traefik
- `TRAEFIK_NETWORK` The network of Traefik
- `TRAEFIK_ROUTER` The router of Traefik

### Nginx
- `UPSTREAM_DOMAIN` The domain of the upstream server
- `UPSTREAM_PORT` The port of the upstream server
- `UPSTREAM_HOST_HEADER` The host header of the upstream server, usually the same as the domain, but in some cases, it can be different
- `UPSTREAM_PROTOCOL` The protocol of the upstream server
- `MAX_CACHE_SIZE` The maximum size of the cache
- `CACHE_DURATION` The duration of the cache
- `IN_RAM_SIZE` The size of the in-ram cache

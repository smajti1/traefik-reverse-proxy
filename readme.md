## How to Start

    cp .env.example .env

Create the external network "gateway"

    docker network create gateway

Start docker container

    docker-compose -f docker-compose.prod.yml up --detach

## Development

    docker-compose -f docker-compose.dev.yml up --detach

### create `*.local` private self-signed certificate files

    openssl req -x509 -newkey rsa:4096 -nodes -keyout certs/_wildcard.local.key -out certs/_wildcard.local.crt -days 365 -config certs/minimal.cnf

##### Or use https://github.com/FiloSottile/mkcert#installation

Only important question is with `Common Name (e.g. server FQDN or YOUR name)`
and for development answer is `*.local`

## Shortcuts

- Traefik cli help command `docker-compose exec reverse-proxy traefik -h`
- Dashboard link `http://localhost:8080/dashboard/#/`
- Show logs `docker-compose logs -f`
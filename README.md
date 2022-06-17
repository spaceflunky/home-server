
# Requirements

## Dynamic DNS

If you want to access your services remotely without opening unsecured `http` ports on your router (__DO NOT do this__), you'll need to use the `/vpn` stack (`wireguard` and `cloudflare-ddns`). To connect to your Wireguard VPN using a domain name, you'll need to:

1) own a domain
2) set it up with Cloudflare DNS, and
3) create an API key to use with `cloudflare-ddns`

I leave this exercise to the reader.

# Config

### Setup network

`docker network create proxy`

### Create and **EDIT** `.env` file

```
cp .env.sample .env
nano .env
```

### Starting services

For each "stack":

```
cd $stack_dir
docker compose --env-file ../.env up -d
```

# Stacks

## `/backup`

### Duplicati

https://www.duplicati.com/

https://hub.docker.com/r/linuxserver/duplicati

## `/dashboard`

### Heimdall

https://heimdall.site/

https://hub.docker.com/r/linuxserver/heimdall

## `/media`

### Jellyfin

https://jellyfin.org/

https://hub.docker.com/r/linuxserver/jellyfin

## `/notify`

### Gotify

https://gotify.net/

https://hub.docker.com/r/gotify/server

## `/portainer`

### Portainer

https://www.portainer.io/

https://docs.portainer.io/v/ce-2.9/start/install/server/docker/linux

## `/proxy`

### docker-socket-proxy

https://github.com/Tecnativa/docker-socket-proxy

### Traefik

https://traefik.io/

https://hub.docker.com/_/traefik

## `/smart-home`

### Home Assistant

https://www.home-assistant.io/

https://hub.docker.com/r/linuxserver/homeassistant

## `/torrents`

### Transmission

https://transmissionbt.com/

https://hub.docker.com/r/linuxserver/transmission

### Flood

https://flood.js.org/

https://hub.docker.com/r/jesec/flood

### Jackett

https://github.com/Jackett/Jackett

https://hub.docker.com/r/linuxserver/jackett

### Radarr

https://radarr.video/

https://hub.docker.com/r/linuxserver/radarr

### Sonarr

https://sonarr.tv/

https://hub.docker.com/r/linuxserver/sonarr

### Ombi

https://ombi.io/

https://hub.docker.com/r/linuxserver/ombi/

## `/vpn`

### cloudflare-ddns

https://github.com/oznu/docker-cloudflare-ddns

https://hub.docker.com/r/oznu/cloudflare-ddns/

### Wireguard

https://www.wireguard.com/

https://hub.docker.com/r/linuxserver/wireguard
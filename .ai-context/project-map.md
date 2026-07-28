# Project map

## Shape

This repository is a catalog of independent Docker Compose deployment templates, not one application. Each top-level template directory is normally self-contained and is anchored by a `docker-compose.yaml`; a few templates contain nested variants or supporting configuration.

## Top-level areas

- **Application stacks:** `Activepieces`, `AFFiNE`, `Authentik`, `Bitwarden`, `Budibase`, `Cal.com`, `CodeX.docs`, `Docmost`, `Fireshare`, `Gotify`, `Moodle`, `Planka`, `PWPusher`, `Semaphore`, `Trilium`, `UpTimeKuma`, `Zabbix`.
- **Databases and messaging:** `InfluxDB`, `MariaDB`, `MySQL-phpMyAdmin`, `Obsidian-LiveSync`, `Redis`, `RabbitMQ`, `Nextcloud-MariaDB`.
- **Networking and access:** `Bind9`, `Cloudfalre-tunnel`, `Cloudflare-ddns`, `HAProxy`, `Homeassistant`, `NGINX-Web`, `NGINX-ReverseProxy`, `Taiscale`, `Teleport`, `Traefik`, `Twingate`.
- **Observability and operations:** `Crowdsec`, `Dockge`, `Duplicati`, `Grafana-InfluxDB`, `GreyLog`, `Homepage`, `Kestra`, `Rancher`, `Watchtower`, `Whats-up-docker`.
- **Media and file services:** `Eclipse Mosquitto`, `FileZilla Server`, `Jellyfin + nzb`, `Jellyfin + qBittorent`, `Netboot.xyz`, `PiHole`.
- **Nested variants:** `Pterodactyl/Pterodactyl-Panel`, `Pterodactyl/Pterodactyl-Wing`, `Pterodactyl/Blueprint`, and `RabbitMQ/normal` plus `RabbitMQ/cluster`.

## Navigation

- Read the compose file in the target template directory first.
- Check its adjacent `.env` or `.env.example` by variable names only; these files may contain credentials.
- Read adjacent `config/` files for Bind9, HAProxy, Homepage, Teleport, Traefik, or PWPusher templates.
- Use `indexes/files.json` for the complete template inventory and `architecture.md` for service-boundary patterns.
- `.ai-context/` is the canonical shared context. Source files and explicit project rules remain authoritative.

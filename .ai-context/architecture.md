# Architecture

## Deployment model

The repository contains 58 standalone Docker Compose definitions. There is no shared application runtime, common library, central service registry, or top-level compose file. A user selects one template directory and runs it independently with Docker Compose.

Each template usually defines one of these shapes:

- A single container with bind-mounted state, such as Redis, Duplicati, or Trilium.
- An application with a database and/or cache, such as Activepieces, AFFiNE, Authentik, Docmost, Planka, and Cal.com.
- A multi-service platform stack, such as Budibase, GreyLog, PowerDNS, Pterodactyl, or the media stacks.
- An infrastructure or network edge component, such as Bind9, HAProxy, NGINX, Traefik, Teleport, Twingate, and Cloudflare connectors.

## Service and data flow

Compose service dependencies are expressed with `depends_on`, legacy `links`, shared networks, and service hostnames. Persistent state is stored in named volumes or host bind mounts. Configuration enters through `.env`, `env_file`, inline environment interpolation, mounted config directories, or Docker labels.

Common integration boundaries include:

- PostgreSQL, MariaDB, MySQL, MongoDB, Redis, CouchDB, and InfluxDB backing application services.
- Reverse proxies and certificate automation through NGINX, Traefik, HAProxy, Cloudflare Tunnel, or Cloudflare DDNS.
- Docker Engine access through `/var/run/docker.sock` in management, discovery, or worker templates.
- Host networking, TUN devices, privileged mode, Linux capabilities, and fixed host ports for infrastructure templates.

## Change and removal guidance

To add or change a template, update the template directory as one unit: compose definition, environment variable contract, mounted configuration, and any adjacent operational notes. There is no central index that must be updated, but `README.md` and `.ai-context/indexes/files.json` should be updated when the catalog changes.

To remove a template, first identify named volumes, host bind mounts, external networks, DNS records, reverse-proxy routes, and dependent stacks. Remove the compose/config files only after preserving or migrating data and credentials. Do not delete shared external networks or host data as part of a repository cleanup. Rollback is restoring the template files and reconnecting the previously retained volumes/configuration.

## Evidence boundaries

The architecture is inferred from repository layout and compose/config files. No containers were started and no live Docker environment was inspected.

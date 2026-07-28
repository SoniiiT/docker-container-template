# Dependencies

## Runtime

- Docker Engine and Docker Compose are required for every template.
- The repository has no language runtime, package manager, application build, or library dependency of its own.
- Images are pulled from Docker Hub, GitHub Container Registry, Amazon ECR, LinuxServer, vendor registries, and project-specific registries. Image names and tags are listed in each compose file.

## External systems represented by templates

- Databases and stores: PostgreSQL, MariaDB, MySQL, MongoDB, Redis, CouchDB, and InfluxDB.
- Networking and identity: Cloudflare, Twingate, Tailscale, Teleport, Traefik, NGINX, HAProxy, and Bind9.
- Operations and monitoring: Grafana, Graylog, CrowdSec, Zabbix, Watchtower, Dockge, Rancher, and Kestra.
- Application vendors: Activepieces, AFFiNE, Authentik, Bitwarden, Budibase, Cal.com, Docmost, Moodle, Pterodactyl, and others.

## Repository automation

`renovate.json` extends Renovate's recommended configuration. No workflow file or other automated validation configuration was found.

## Configuration inputs

There are 24 environment-like files, including `.env`, `settings.env`, and `.env.example`. Their values are intentionally not indexed. Consumers must provide the variables required by the selected compose file, especially database passwords, application secrets, API tokens, and connector credentials.

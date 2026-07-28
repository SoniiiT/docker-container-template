# Observed risks

- Many `.env` and `settings.env` files are tracked. Their values were not read or copied, but repository history should be treated as potentially credential-bearing.
- `Bind9/config/named.conf.key` is a tracked key-like file and should be reviewed and rotated if it contains live material.
- `Taiscale/docker-compose.yaml` contains a hardcoded authentication-key-shaped value; rotate it and move credentials to an ignored environment source.
- Pterodactyl compose files and HAProxy configuration contain literal default or credential-shaped settings; replace them before deployment.
- Several templates use `latest`, `stable`, or `develop`, reducing reproducibility and making upgrades implicit.
- Docker socket mounts, `privileged`, broad Linux capabilities, host networking, and fixed public ports expand the attack surface.
- Traefik's example enables an insecure dashboard, and its dynamic example permits TLS verification bypass; these are not production-safe defaults.
- The repository has no automated Compose validation, secret scanning, or CI workflow.

These are repository observations, not a live compromise assessment. Review date: 2026-07-28.

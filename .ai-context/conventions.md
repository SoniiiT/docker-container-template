# Conventions

## Observed implementation conventions

- Compose files use YAML with mixed Compose schema versions and inconsistent quoting/formatting.
- Images are a mixture of pinned versions and mutable tags such as `latest`, `stable`, or `develop`.
- LinuxServer images commonly use `PUID`, `PGID`, and `TZ`; state is usually mounted under an application-specific directory.
- Secrets are commonly supplied by `${VARIABLE}` interpolation or `env_file`, but several templates also contain literal defaults or credentials.
- Compose service names, container names, and network names are generally descriptive and application-specific.
- Comments are often operational guidance copied into the template; comments are in English and German.

## Validation and testing

No unit tests, integration tests, CI workflows, package manifests, or application build scripts were found. The repository's practical validation boundary is per-template Docker Compose parsing and deployment review. For a change, use `docker compose config` with a safe, non-secret environment file and inspect ports, mounts, dependencies, health checks, and image references before deployment.

## Documentation

The root `README.md` is a short German overview and describes selecting a template, editing `docker-compose.yml`, and using `docker-compose up -d` / `down`. Most operational documentation is embedded as YAML comments or adjacent configuration examples rather than separate guides.

## Security conventions and gaps

Secret-bearing `.env` files are tracked in the repository, and key-like configuration files are present. Docker socket mounts, privileged containers, host networking, broad port exposure, insecure dashboards, default credentials, and TLS verification bypasses occur in individual templates. Treat every template as an example requiring an explicit hardening review before production use.

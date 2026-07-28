# Template catalog lifecycle

## Scope

Each template directory is a separately deployable unit. Its compose file, environment contract, mounted configuration, and persistent storage assumptions form one feature boundary.

## Change obligations

- Keep service names, dependency relations, ports, networks, and volume paths internally consistent.
- Update adjacent `.env.example` or variable documentation when adding a required variable; do not commit real secret values.
- Review image tags, health checks, exposed ports, privileges, host mounts, and external networks before release.
- Validate with `docker compose config` using safe placeholder values, then perform a deployment-specific smoke test outside this repository.

## Evidence

Observed across the 58 compose files and supporting configuration files. There is no central registry or automated test suite.

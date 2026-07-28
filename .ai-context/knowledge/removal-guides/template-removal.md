# Removing a template

1. Identify the template's compose file, environment files, nested configuration, named volumes, bind mounts, and external networks.
2. Find operational dependencies outside the repository: reverse-proxy routes, DNS records, monitoring checks, notification hooks, and other stacks that reference its ports or hostnames.
3. Back up or migrate persistent data before deleting files. Repository removal must not delete host directories, Docker volumes, or external networks.
4. Remove the complete template directory or selected variant, then update `README.md` and `.ai-context/indexes/files.json` if the catalog inventory changes.
5. Re-check secret rotation and access revocation for credentials that were used by the removed deployment.

Rollback is restoring the files and reconnecting retained data/configuration. Compatibility risk is highest for shared databases, proxy networks, DNS zones, and media or monitoring integrations.

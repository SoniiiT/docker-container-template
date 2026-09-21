# OpenWolf

This project uses OpenWolf for context management. The always-on rules live in `.claude/rules/openwolf.md`; the hooks handle bookkeeping (anatomy index, memory log, read tracking) automatically.

For the full operating protocol (session handoff, memory discipline, bug logging), load the `openwolf` skill, or read `.wolf/OPENWOLF.md`. Regenerate the session handoff with `/handoff`.


# Claude project context

Use `.ai-context/` as the shared project context, starting with `manifest.json` and `project-map.md`, then the relevant lifecycle guide. It describes independent Docker Compose templates and their configuration boundaries. Source code and explicit project rules remain authoritative; generated summaries must not be treated as more authoritative. Do not read, copy, or expose secret values from `.env`, settings, or key-like files.

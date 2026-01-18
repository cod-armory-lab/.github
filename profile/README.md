# Cod Armory Lab

A player-focused, version-resilient data platform for Call of Duty weapons, attachments, and loadouts.

Cod Armory Lab is designed to keep weapon/build data stable across seasons, patches, and hotfixes so players can reliably compare changes over time — before/after a patch — with full traceability.

## Repositories

- **cod-armory-lab-api** — API and core resolution engine (base → overrides → patch view)
- **cod-armory-lab-data** — Versioned datasets (registry, base data, patch overrides, sources)
- **cod-armory-lab-cli** — Tooling (diff, validation, changelog generation, import/export)
- **cod-armory-lab-web** — Player UI (comparison, loadouts, history) *(optional)*
- **cod-armory-lab-schemas** — Shared contracts (OpenAPI/JSON Schema/Proto) *(optional)*

## Key Concepts

- **Immutable IDs**: technical identifiers never change and are never reused.
- **Patch overrides**: balance updates are applied as versioned overrides rather than rewriting history.
- **Full traceability**: every change is dated, sourced, and reversible.
- **Comparable views**: build accurate “as-of patch” snapshots for analysis and UI.

## Typical Workflow

1. Add or update base entities in `cod-armory-lab-data`
2. Add patch overrides for balance changes
3. Run `cod-armory-lab-cli` to validate and produce diffs/changelogs
4. Serve resolved snapshots through `cod-armory-lab-api`
5. Display comparisons in `cod-armory-lab-web`

## Contributing

- Use PRs for all changes
- Add sources for patch changes (patch notes, season notes, hotfix notes)
- Run validation before submitting

## License

TBD (MIT/Apache-2.0 recommended for open tooling; data licensing depends on sources).

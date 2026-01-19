# Contributing to Cod Armory Lab

> **Play armed. Play smart.**
>
> Cod Armory Lab is player-centric: data and tooling exist only to help players make better loadout decisions.

## Ways to contribute

- Report bugs (API, tooling, data validation)
- Propose features (player value first)
- Submit data updates (patch changes, attachment behavior changes)
- Improve documentation

## Guiding principles

Before opening an issue or PR, ask:
- **Does this help players make a better loadout choice?**
- Does this preserve **history** and **comparability** across patches?
- Are we keeping complexity **transparent** to the player?

## Repo responsibilities (quick map)

- `cod-armory-lab-api` — resolution engine, patch-accurate snapshots
- `cod-armory-lab-data` — base entities, patch overrides, registry, sources
- `cod-armory-lab-web` — player-facing UI (compare, explore)
- (future) `cod-armory-lab-cli` — validation, diffs, changelogs

## Branch & PR workflow

1. Create an issue first (unless it’s a trivial typo)
2. Create a branch from `main`
3. Open a PR early (Draft is OK)
4. Ensure checks pass and add/update documentation if needed
5. Request review (CODEOWNERS will help route it)

### Branch naming

Use one of:
- `feat/<short-scope>`
- `fix/<short-scope>`
- `data/<patch-id-or-scope>`
- `docs/<short-scope>`
- `chore/<short-scope>`

Examples:
- `feat/loadout-compare-endpoint`
- `data/mwiii-s05-hotfix-2024-07-24`
- `fix/resolve-override-precedence`

## Commit message convention

We use **Conventional Commits**:

- `feat:` new functionality
- `fix:` bug fix
- `data:` data-only changes (patches, registry, overrides)
- `docs:` documentation
- `chore:` maintenance (CI, tooling, refactor with no behavior change)
- `test:` tests
- `ci:` CI config

Examples:
- `feat(api): add patch snapshot endpoint`
- `data: add S05 hotfix overrides (MWIII)`
- `fix(data): correct attachment id alias mapping`
- `docs: clarify patch override precedence`

## Data updates rules (important)

When changing `cod-armory-lab-data`:
- Never delete or reuse immutable IDs
- Prefer patch overrides over rewriting base history
- Add a **source** (patch notes link, season notes, etc.)
- Include a short “before/after” summary in the PR

## Reviews

- API changes: at least 1 maintainer review
- Data changes: at least 1 data curator review
- Anything impacting schemas/contracts: maintainers + affected area owner

## Definition of Done

- Clear player value (or maintenance rationale)
- Tests/validation pass (when applicable)
- Docs updated if behavior changes
- PR description includes context & impact

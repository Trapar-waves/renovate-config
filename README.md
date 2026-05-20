# Trapar-waves Renovate Config

![GitHub last commit](https://img.shields.io/github/last-commit/Trapar-waves/renovate-config)
![Renovate](https://img.shields.io/badge/renovate-enabled-blue)

---

[中文](./readme/README-CN.md) | [日本語](./readme/README-JP.md) | [Русский язык](./readme/README-RU.md)

> Organization-wide Renovate preset for [Trapar-waves](https://github.com/Trapar-waves) template repositories—a single source of truth for dependency update policies.

## Usage

In each template repository’s `renovate.json`:

```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": ["github>Trapar-waves/renovate-config"]
}
```

Renovate loads [`default.json`](./default.json) from the root of this repository.

## Policy summary

- Based on `config:best-practices` (Actions digest pinning, weekly lockfile maintenance, and more)
- `minimumReleaseAge`: 1 day, `internalChecksFilter`: strict
- `rangeStrategy`: bump
- Grouped updates: React, Rsbuild, `@trapar-waves/*`
- Major updates require approval in the Dependency Dashboard before a PR is opened

## Local validation

```bash
npx --yes -p renovate renovate-config-validator default.json
```

## Notes

- `minimumReleaseAge` has limited support for lock file maintenance updates; see the [Renovate documentation](https://docs.renovatebot.com/key-concepts/minimum-release-age).
- After changes to `default.json` are merged into `main`, repositories that extend this preset pick them up on the next Renovate run.

## Versioning

You can pin a release tag, for example: `github>Trapar-waves/renovate-config#v1.0.0`.

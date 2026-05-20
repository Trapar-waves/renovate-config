# Trapar-waves Renovate Config

![GitHub last commit](https://img.shields.io/github/last-commit/Trapar-waves/renovate-config)
![Renovate](https://img.shields.io/badge/renovate-enabled-blue)

---

[English](../README.md) | [中文](./README-CN.md) | [日本語](./README-JP.md)

> Общий Renovate preset для шаблонных репозиториев организации [Trapar-waves](https://github.com/Trapar-waves)—единый источник политик обновления зависимостей.

## Использование

В `renovate.json` каждого шаблонного репозитория:

```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": ["github>Trapar-waves/renovate-config"]
}
```

Renovate загружает [`default.json`](../default.json) из корня этого репозитория.

## Кратко о политике

- На базе `config:best-practices` (фиксация digest для Actions, еженедельное обслуживание lockfile и др.)
- `minimumReleaseAge`: 1 день, `internalChecksFilter`: strict
- `rangeStrategy`: bump
- Группировка: React, Rsbuild, `@trapar-waves/*`
- Major-обновления требуют одобрения в Dependency Dashboard перед созданием PR

## Локальная проверка

```bash
npx --yes -p renovate renovate-config-validator default.json
```

## Примечания

- `minimumReleaseAge` ограниченно поддерживается для обновлений lock file maintenance; см. [документацию Renovate](https://docs.renovatebot.com/key-concepts/minimum-release-age).
- После слияния изменений `default.json` в `main` репозитории с `extends` этого preset применят их при следующем запуске Renovate.

## Версионирование

Можно закрепить тег, например: `github>Trapar-waves/renovate-config#v1.0.0`.

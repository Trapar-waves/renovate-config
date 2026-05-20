# Trapar-waves Renovate Config

![GitHub last commit](https://img.shields.io/github/last-commit/Trapar-waves/renovate-config)
![Renovate](https://img.shields.io/badge/renovate-enabled-blue)

---

[English](../README.md) | [日本語](./README-JP.md) | [Русский язык](./README-RU.md)

> [Trapar-waves](https://github.com/Trapar-waves) 组织模板仓库的 Renovate 共享 preset，单一来源维护依赖更新策略。

## 使用方式

在各模板仓库的 `renovate.json` 中：

```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": ["github>Trapar-waves/renovate-config"]
}
```

Renovate 会加载本仓库根目录的 [`default.json`](../default.json)。

## 策略摘要

- 基于 `config:best-practices`（Actions digest 固定、每周 lockfile 维护等）
- `minimumReleaseAge`: 1 天，`internalChecksFilter`: strict
- `rangeStrategy`: bump
- 分组：React、Rsbuild、`@trapar-waves/*`
- Major 更新需在 Dependency Dashboard 中审批后才会开 PR

## 本地校验

```bash
npx --yes -p renovate renovate-config-validator default.json
```

## 注意事项

- `minimumReleaseAge` 对 lock file maintenance 类更新支持有限，详见 [Renovate 文档](https://docs.renovatebot.com/key-concepts/minimum-release-age)。
- 修改 `default.json` 合并到 `main` 后，所有 `extends` 本 preset 的仓库会在下一轮 Renovate 运行中生效。

## 版本

可选通过 tag 钉版本，例如：`github>Trapar-waves/renovate-config#v1.0.0`。

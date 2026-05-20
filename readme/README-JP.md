# Trapar-waves Renovate Config

![GitHub last commit](https://img.shields.io/github/last-commit/Trapar-waves/renovate-config)
![Renovate](https://img.shields.io/badge/renovate-enabled-blue)

---

[English](../README.md) | [中文](./README-CN.md) | [Русский язык](./README-RU.md)

> [Trapar-waves](https://github.com/Trapar-waves) 組織のテンプレートリポジトリ向け Renovate 共有 preset。依存関係の更新ポリシーを一元管理します。

## 使い方

各テンプレートリポジトリの `renovate.json` に次を記述します。

```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": ["github>Trapar-waves/renovate-config"]
}
```

Renovate は本リポジトリルートの [`default.json`](../default.json) を読み込みます。

## ポリシー概要

- `config:best-practices` をベース（Actions digest の固定、週次 lockfile メンテナンスなど）
- `minimumReleaseAge`: 1 日、`internalChecksFilter`: strict
- `rangeStrategy`: bump
- グループ化: React、Rsbuild、`@trapar-waves/*`
- Major 更新は Dependency Dashboard での承認後に PR が作成されます

## ローカル検証

```bash
npx --yes -p renovate renovate-config-validator default.json
```

## 注意事項

- `minimumReleaseAge` は lock file maintenance 系の更新ではサポートが限定的です。詳細は [Renovate ドキュメント](https://docs.renovatebot.com/key-concepts/minimum-release-age) を参照してください。
- `default.json` の変更が `main` にマージされると、本 preset を `extends` するリポジトリは次回の Renovate 実行で反映されます。

## バージョン固定

タグでバージョンを固定できます。例: `github>Trapar-waves/renovate-config#v1.0.0`

---
title: wacz-validator-corpus
description: wacz-validator の validation rule を検証するための WACZ 標本集。対照のほかは意図的に壊してあります。
---

[wacz-validator](https://uraitakahito.github.io/wacz-validator/ja/) の validation rule を
検証するための WACZ 標本集です。

## 「正しいアーカイブ」を集めたものではありません

名前が `good` で始まる標本が対照で、既定の profile（`spec`）では valid になります。
それ以外の標本はすべて意図的に壊してあり、それぞれが踏ませる rule は[カタログ](/catalogue/)にあります。

これは wacz-validator に WACZ 形式のサンプルデータを提供するものです。
**意図的に壊した標本については「何も指摘が出ない」ことが失敗**です。

そのうち 1 本は壊れているというより、別の仕様に忠実です ——
`datapackage-schema-only` は Data Package v2 として正しい descriptor で、
v2 が廃止した `profile` を WACZ 1.1 が要求するために失敗します。

## 「壊れている」と「無効」は別です

`datapackage-frictionless-bad-name.wacz` の判定は `valid: true` です。
`resources[0].name` が `data.warc.gz` ではなく `DATA.warc.gz`（大文字）で、
Frictionless v1 のスキーマはこれを許しませんが、それは `warning` であり、
warning は valid を覆しません。

つまり「指摘がある」と「無効である」は別の軸です。[カタログ](/catalogue/)は
その両方を記録しています。

## 中身

```
fixtures/            全標本（Git LFS）
manifest.json        wacz-validator が実際に報告した結果
scripts/
  check-manifest.mjs manifest ↔ fixtures の整合チェック（依存ゼロ）
docs-site/           このサイト
```

標本も manifest も手書きではありません —— [再生成](/regenerating/)を参照。

## 次に読むもの

- **[はじめに](/getting-started/)** —— アーカイブの入手方法（Git LFS にあります）
- **[カタログ](/catalogue/)** —— 全標本と、それぞれが何に違反するか
- **[使い方](/using-it/)** —— rule を書くときに corpus をどう使うか
- **[manifest](/manifest/)** —— スキーマと、`defaultProfile` の意味
- **[再生成](/regenerating/)** —— 標本の作られ方と、何が破壊されるか
- **[整合チェック](/checks/)** —— 3 つの検査がそれぞれ何を見ているか

---
title: wacz-validator-corpus
description: WACZ specimens for testing wacz-validator validation rules — all but the controls broken on purpose.
---

A collection of WACZ specimens for exercising [wacz-validator](https://uraitakahito.github.io/wacz-validator/)
validation rules.

## It is not a collection of good archives

The specimens whose names start with `good` are the controls: they are valid
under the default `spec` profile. Every other specimen is broken on purpose, and
the [catalogue](/catalogue/) lists the rule each one is meant to trip.

This provides WACZ-format sample data to wacz-validator. For every specimen that
is broken on purpose, **producing no findings is a failure**.

One of them is not broken so much as loyal to a different spec:
`datapackage-schema-only` is a valid Data Package v2 descriptor, and it fails
only because WACZ 1.1 requires the `profile` that v2 removed.

## Broken is not the same as invalid

`datapackage-frictionless-bad-name.wacz` reports `valid: true`. Its
`resources[0].name` is `DATA.warc.gz` instead of `data.warc.gz` — uppercase,
which the Frictionless v1 schema forbids — but that is a `warning`, and warnings
do not overturn validity.

So "has a finding" and "is invalid" are separate axes. The
[catalogue](/catalogue/) records both.

## What is here

```
fixtures/            every specimen (Git LFS)
manifest.json        what wacz-validator actually reports for each one
scripts/
  check-manifest.mjs manifest ↔ fixtures consistency (no dependencies)
docs-site/           this site
```

Neither the specimens nor the manifest are written by hand — see
[Regenerating](/regenerating/).

## Where to go next

- **[Getting started](/getting-started/)** — obtaining the archives (they are in Git LFS)
- **[Catalogue](/catalogue/)** — every specimen and what it violates
- **[Using it](/using-it/)** — reaching for the corpus while writing a rule
- **[manifest](/manifest/)** — the schema, and what `defaultProfile` means
- **[Regenerating](/regenerating/)** — how specimens are produced, and what gets destroyed
- **[Checks](/checks/)** — the three checks and what each one covers

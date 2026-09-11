---
title: Using it while developing a rule
description: How to reach for the corpus while writing or changing a rule.
---

Point wacz-validator at a specimen directly:

```sh
wacz-validator-validate --profile spec       path/to/corpus/fixtures/<name>.wacz
wacz-validator-validate --profile lenient    path/to/corpus/fixtures/<name>.wacz
```

Running the same archive under two profiles is the quickest way to see what a
profile actually re-grades — the [Profiles](https://uraitakahito.github.io/wacz-validator/profiles/) page explains
what that means, and the [Rules](https://uraitakahito.github.io/wacz-validator/rules/) table lists which rules have
overrides at all.

---
layout: default
title: YAML Aliases
parent: Configure a client dataset
grand_parent: Datasets
---

## YAML Aliases

Aliases can be used to reduce duplication of keys in the YAML file.

```yaml
marketing: &marketing
    type: "marketing"
    decimals: 0
    enabled: true

database: &database
    type: "database"
    decimals: 2
    enabled: false

vars:
    google_ads:
        <<: *marketing
        name: "Google Ads"
    postgres:
        <<: *database
        name: "PostgreSQL"
```

This makes it easy to reuse keys across the file.

[More details about anchors and aliases in YAML](https://www.educative.io/blog/advanced-yaml-syntax-cheatsheet#anchors:~:text=YAML%20Anchors%20and%20Alias)

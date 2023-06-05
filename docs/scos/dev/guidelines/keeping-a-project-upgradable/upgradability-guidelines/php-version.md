---
title: PHP version
description: Reference information for evaluator tools.
template: howto-guide-template
---

This guide describes how to resolve problems surrounding the allowed and consistent PHP version being used in different project parts.

## Problem description

The PHP version is declared in different configuration files and used by dependencies.
You need to be sure that all those items have a PHP version that is consistent and supported by Spryker..

PHP versions are checked in:
- `composer.json`
- Config deploy files `deploy.**.yml`
- Installed PHP version
- [Spryker SDK](https://docs.spryker.com/docs/sdk/dev/spryker-sdk.html) php versions

## Example of code that causes an upgradability error

composer.json
```json
{
  "name": "spryker-shop/b2c-demo-shop",
  "description": "Spryker B2C Demo Shop",
  "license": "proprietary",
  "require": {
    "php": ">=8.2",
    ...
  }
}
```

deploy.dev.yaml
```yaml
...
image:
    tag: spryker/php:8.2-alpine3.12
    php:
        ini:
            "opcache.revalidate_freq": 0
            "opcache.validate_timestamps": 0
...
```

### Related error in the Evaluator output

```shell
===================
PHP VERSION CHECKER
===================

+---+-----------------------------------------------------------------------------+--------------------------------------------------------+
| # | Message                                                                     | Target                                                 |
+---+-----------------------------------------------------------------------------+--------------------------------------------------------+
| 1 | Composer json PHP constraint ">=8.1" does not match allowed php versions    | tests/Acceptance/_data/InvalidProject/composer.json    |
+---+-----------------------------------------------------------------------------+--------------------------------------------------------+
| 2 | The deploy file uses a not allowed PHP image version "spryker/php:7.2-alpine3.12" | tests/Acceptance/_data/InvalidProject/deploy.yml       |
|   | The image tag must contain an allowed PHP version (image:abc-8.0)                  |                                                        |
+---+-----------------------------------------------------------------------------+--------------------------------------------------------+
| 3 | Not all the targets have same PHP versions                                  | Current php version $phpVersion: php7.4                     |
|   |                                                                             | tests/Acceptance/_data/InvalidProject/composer.json: - |
|   |                                                                             | tests/Acceptance/_data/InvalidProject/deploy**.yml: -  |
|   |                                                                             | SDK php versions: php7.4, php8.0                       |
+---+-----------------------------------------------------------------------------+--------------------------------------------------------+
```

### Resolving the error

To resolve the issue:
1. Use a PHP version that is allowed in:
   - `composer.json`
   - Config deploy files `deploy.**.yml`
   - Installed PHP version
   - SDK php versions
2. Make sure that all the items above have consistent PHP versions.
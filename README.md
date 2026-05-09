# UB Symfony Recipes

Private Flex recipe repository for [ub-unibe-ch](https://github.com/ub-unibe-ch) Symfony bundles.

## Usage

Add the following to `composer.json` in your Symfony project:

```json
"extra": {
    "symfony": {
        "endpoint": [
            "https://api.github.com/repos/ub-unibe-ch/symfony-recipes/contents/index.json",
            "flex://defaults"
        ]
    }
}
```

Then install bundles normally — Flex will apply the recipe automatically:

```bash
composer require ub-unibe-ch/translatable-entities-bundle
```

## How it works

- Recipe source files live under `<vendor>/<package>/<version>/`
- On every push to `main`, a GitHub Action compiles them into `index.json` and the recipe JSON files using [symfony-tools/recipes-checker](https://github.com/symfony-tools/recipes-checker)

## Recipes

| Package | Version | Description |
|---|---|---|
| `ub-unibe-ch/translatable-entities-bundle` | `1.0` | Registers bundle, adds `.env` locale vars, copies config stub |

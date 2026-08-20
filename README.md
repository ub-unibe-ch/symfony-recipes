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
- On every pull request to `main`, a GitHub Action compiles them into `index.json` and the recipe JSON files using [symfony-tools/recipes-checker](https://github.com/symfony-tools/recipes-checker) and commits the result back to the PR branch

## Recipes

| Package | Version | Description |
|---|---|---|
| `ub-unibe-ch/bootstrap-bundle` | `1.0` | Adds a `tests/bootstrap-bundle/panther-router.php` Panther workaround and wires it up via `PANTHER_WEB_SERVER_ROUTER` in `.env.test`, unconditionally (harmless if `symfony/panther` is not used) |
| `ub-unibe-ch/dspace-api-bundle` | `0.0` | Registers bundle, adds `.env` DSpace connection vars, copies config stub |
| `ub-unibe-ch/job-report-bundle` | `1.0` | Registers bundle, adds `.env` report vars, copies config stub and Messenger middleware config |
| `ub-unibe-ch/translatable-entities-bundle` | `0.0` | Registers bundle, adds `.env` locale vars, copies config stub |

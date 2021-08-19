# SocialGouv Renovate Config

Our shared renovate config

https://app.renovatebot.com/dashboard#github/SocialGouv/renovate-config/

## Usage

Choose you `preset` :

- `github>SocialGouv/renovate-config`: daily maintenance
- `github>SocialGouv/renovate-config:light`: weekly maintenance

Set your preset in `.github/renovate.json`

```json
{
  "enabled": true,
  "extends": ["github>SocialGouv/renovate-config"]
}
```

## Rules

> Description of the rules we need.
> 🔗 means _included in the default config_.

- 🔗 `github>SocialGouv/renovate-config//rules/group-deployment-tools` :
  Group all the tools needed to deploy on the SocialGouv infra.  
  Mainly the depedencies of your `.k8s/package.json`.

  See https://github.com/SocialGouv/kosko-charts/

- 🔗 `github>SocialGouv/renovate-config//rules/node-lts-version` :
  Restrict the node versions to the current Active LTS or Maintenance LTS releases.
  See https://nodejs.org/en/about/releases/

- 🔗 `github>SocialGouv/renovate-config//rules/postgres-azure-version` :
  Restrict the postgres versions to the supported Azure PostgreSQL major versions.
  See https://docs.microsoft.com/en-us/azure/postgresql/concepts-supported-versions

## Additionnals presets

- `github>SocialGouv/renovate-config:socialgouv-data` : automerge social-gouv/data packages

```json
{
  "enabled": true,
  "extends": [
    "github>SocialGouv/renovate-config:light",
    "github>SocialGouv/renovate-config:socialgouv-data"
  ]
}
```

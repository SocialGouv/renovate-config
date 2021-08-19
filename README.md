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
> :handshake: means _included in the default config_.  
> :sloth: means _included in the light config_.

- :handshake: [`github>SocialGouv/renovate-config//rules/group-deployment-tools`](./rules/group-deployment-tools.json) :
  Group all the tools needed to deploy on the SocialGouv infra.  
  Mainly the depedencies of your `.k8s/package.json`.  
  See https://github.com/SocialGouv/kosko-charts/

- :sloth: [`github>SocialGouv/renovate-config//rules/group-devdeployment-non-major`](./rules/group-devdeployment-non-major.json) :
  Group all non major `package.json` dependencies by dependecy type.  
  On per for the `dependencies` another for the `devDependencies`

- :handshake: [`github>SocialGouv/renovate-config//rules/node-lts-version`](./rules/node-lts-version.json) :
  Restrict the node versions to the current Active LTS or Maintenance LTS releases.
  See https://nodejs.org/en/about/releases/

- :handshake: [`github>SocialGouv/renovate-config//rules/postgres-azure-version`](./rules/postgres-azure-version.json) :
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

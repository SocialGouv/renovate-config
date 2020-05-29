# SocialGouv Renovate Config

Our shared renovate config

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

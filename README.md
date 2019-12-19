# renovate-config

Our shared renovate config

## usage

Add `.renovaterc.json` to your project 

```json
{
  "enabled": true,
  "extends": [
    "github>SocialGouv/renovate-config",
    ":automergeAll"
  ],
  "packageRules": [
    {
      "groupName": "SocialGouv",
      "packagePatterns": [
        "^@socialgouv/"
      ]
    }
  ]
}
```

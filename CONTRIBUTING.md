# Contributing to SocialGouv/renovate-config

## DevExp

We use nodejs tools to help developing, testing the renovate config.

```sh
# Install all with
$ yarn

# format the files with
$ yarn format

# test the configuration with
$ yarn test
```

## Create a new rule

1. Add file with the rule name in the [rules folder](./rules).

```js
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "packageRules": [
    {
      // Your rule here
    }
  ]
}
```

1. Add your rule to a preset (like the [default.json](./default.json) for example).

```js
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": [
    // [...]
    "local>SocialGouv/renovate-config//rules/<my_rule>"
    // [...]
  },
  // [...]
}
```

1. Add script to test the configuration of this rule in the [package.json](./package.json).

```js
// [...]
  "scripts": {
    // [...]
    "validate:rules/<my_rule>": "RENOVATE_CONFIG_FILE=rules/<my_rule>.json renovate-config-validator",
    // [...]
  },
// [...]
```

1. Add a link with a short description of what it does in the [README.md](./README.md).

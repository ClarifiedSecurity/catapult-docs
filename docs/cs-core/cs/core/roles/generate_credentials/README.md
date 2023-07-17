# Requirements

## Roles

none

## Usage

This role is already included in start.yml

It will save admin_accounts, user_accounts, domain_user_accounts list to Vault and if need be generates random passwords for users. It can also be used to generate & save random secrets to vault by including `extra_secrets` list with `group_vars` or `host_vars`

Save a secret with a random generated password

```yml
extra_secrets:
  - secret_key_name: MySecretToken
```

Save a secret with a pregenerated password or lookup. You should NEVER write passwords in plain text to configuration files. Use some typo of lookup instead.

```yml
extra_secrets:
  - secret_key_name: MySecretToken
    secret_key_value: Password123
```

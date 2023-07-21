# Requirements

## Roles

none

## Usage

Include the following dict with the role to save the values in the dict to the default location in Vault. If the key already exists it will NOT be overwritten with the new value, unless `autogenerated_secret` var is set to true. `autogenerated_secret` is used for secrets that cannot be set manually, like certain API keys and service tokens.

Generates a random password for the secrets and save them to Vault:

```yml
secrets:
  - key: MySecretToken1
    value: "{{ lookup('password', '/dev/null length=32 chars=ascii_letters,digits') }}"
  - key: MySecretToken2
    value: "{{ lookup('password', '/dev/null length=32 chars=ascii_letters,digits') }}"
```
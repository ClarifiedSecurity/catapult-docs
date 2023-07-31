# updates

This role is used to updated the operating system packages. Currently supported operating systems are: Ubuntu/Debian, Windows & Arch Linux.

## Requirements

None

## Role Variables

Refer to the [defaults/main.yml](https://github.com/ClarifiedSecurity/clarified.core/blob/main/clarified/core/roles/updates/defaults/main.yml) file for a list of variables and their default values.

## Dependencies

None

## Example

```shell
# Use the existing Catapult CLI alias to only run this role for a specific host.
ctp-update-os <inventpry_hostname>
```

```yml
# Use the role in a playbook.
- name: Update the operating system
  ansible.builtin.include_role:
    name: clarified.core.updates
```

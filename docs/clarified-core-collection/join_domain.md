# join_domain

This is a role for adding Windows and Linux hosts to Active Directory (AD) domains.

## Requirements

A variable called `domain` or `ad_domain_name` (if the DNS domain name does not match the AD domain name) must be defined pointing to the AD domain name.

## Role Variables

Refer to the [defaults/main.yml](https://github.com/ClarifiedSecurity/clarified.core/blob/main/clarified/core/roles/join_domain/defaults/main.yml) file for a list of variables and their default values.

One special variable not defined in defaults is `computer_ou`. This variable is used to specify the OU where the computer object should be created. If this variable is not defined, the computer object will be created in the default Computers container.

## Dependencies

Required an Active Directory domain controller to be installed and available.

## Example

```yaml
- name: Joining domain
  ansible.builtin.include_role:
    name: clarified.core.join_domain

- name: Joining domain with custom values
  ansible.builtin.include_role:
    name: clarified.core.join_domain
  vars:
    domain: example.com
    computer_ou: OU=Computers,DC=example,DC=com

- name: Joining domain with custom values and credentials
  ansible.builtin.include_role:
    name: clarified.core.join_domain
  vars:
    domain: example.com
    computer_ou: OU=Computers,DC=example,DC=com
    domain_join_user: domain_join_user # This is just the username. The domain name will be appended automatically.
    domain_join_password: domain_join_password
```

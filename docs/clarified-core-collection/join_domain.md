# join_domain

This is a role for:

- Adding Windows and Linux hosts to Active Directory (AD) domains.
- Fixing broken AD domain joins and re-joining machines to domain.

## Requirements

Following variables are required:

- `domain` - Points to the AD domain name that matches your environments DNS domain.
- `ad_domain_name` - Points to the AD domain name if it does **NOT** match your environments DNS domain.
- `domain_admin_username` - Username of an account that has privileges to join computers to the domain and create/delete computer objects.
- `domain_admin_password` - Password of the domain_admin_username.

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

# Ansible Collection - cs.core

## TLDR

This is an Ansible collection consisting of some roles and a an inventory plugin for [Providentia](https://github.com/ClarifiedSecurity/Providentia) maintained by Clarified Security. It is a core part of [Catapult](https://github.com/ClarifiedSecurity/Catapult) but can be used independently.

For each role under the `cs/core/roles` folder the name should be self explanatory. To use the role include it with `dependencies` or `include_role` task, using the format `cs.core.name_of_the_role`

Each role contains a README.md file with more information about the role. Refer to the role defaults to see what variables are available.

## Examples

Including role from `vm/"name"/tasks/main.yml` This includes the cs.core.get_ip role using the `ansible.builtin.include_role` task.

```yml
- name: Getting the machine IP...
  include_role:
    name: cs.core.get_ip
```

Including role from `vm/"name"/meta/main.yml` This includes the cs.core.get_ip with meta.

```yml
dependencies:
  - role: cs.core.get_ip
```

### TBC

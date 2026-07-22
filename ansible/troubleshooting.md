# Ansible : Troubleshooting

## Version and Configuration

```bash
ansible --version
ansible-config dump --only-changed
ansible-inventory --graph
ansible-galaxy collection list
```

## Connectivity

```bash
ssh -vvv user@host
ansible host -m ansible.builtin.ping -vvvv
ansible host -m ansible.builtin.raw -a 'python3 --version' -vvvv
```

## Playbook Diagnostics

```bash
ansible-playbook site.yml --syntax-check
ansible-playbook site.yml --list-hosts
ansible-playbook site.yml --list-tasks
ansible-playbook site.yml --check --diff
ansible-playbook site.yml -vvvv
```

## Variables

```yaml
- name: Inspect variable
  ansible.builtin.debug:
    var: variable_name

- name: Inspect host variables
  ansible.builtin.debug:
    var: hostvars[inventory_hostname]
```

## Common Failures

```text
UNREACHABLE
  Check inventory address, SSH, credentials, firewall and host keys.

Missing sudo password
  Use --ask-become-pass or configure privilege escalation correctly.

Python interpreter not found
  Set ansible_python_interpreter or bootstrap Python with raw.

Module not found
  Install the required collection and use its fully qualified name.

Undefined variable
  Inspect inventory, group_vars, host_vars, defaults and extra variables.

Template error
  Validate Jinja2 syntax and inspect referenced variables.

Vault decryption failed
  Verify the vault ID and password source.
```

## Linting

```bash
ansible-lint
ansible-lint playbook.yml
```

## Limit the Scope

```bash
ansible-playbook site.yml --limit host.example.com
ansible-playbook site.yml --start-at-task 'Task name'
ansible-playbook site.yml --step
```

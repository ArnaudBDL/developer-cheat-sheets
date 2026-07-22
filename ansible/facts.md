# Ansible : Facts

## Gather Facts

```bash
ansible all -m ansible.builtin.setup
ansible web1.example.com -m ansible.builtin.setup   -a 'filter=ansible_default_ipv4'
ansible all -m ansible.builtin.setup   -a 'gather_subset=min'
```

## Use Facts

```yaml
- name: Display operating system
  ansible.builtin.debug:
    msg: >-
      {{ ansible_facts.distribution }}
      {{ ansible_facts.distribution_version }}
      on {{ ansible_facts.architecture }}
```

## Disable Fact Gathering

```yaml
- name: Fast play without facts
  hosts: all
  gather_facts: false
  tasks:
    - name: Confirm execution
      ansible.builtin.debug:
        msg: Running without gathered facts
```

## Set Facts

```yaml
- name: Calculate application URL
  ansible.builtin.set_fact:
    application_url: "https://{{ inventory_hostname }}:{{ application_port }}"
    cacheable: true
```

## Custom Local Facts

```ini
# /etc/ansible/facts.d/application.fact
[application]
version=1.2.0
environment=production
```

```yaml
- name: Display local fact
  ansible.builtin.debug:
    var: ansible_local.application.application.version
```

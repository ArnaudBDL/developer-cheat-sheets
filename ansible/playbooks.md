# Ansible : Playbooks

## Basic Playbook

```yaml
---
- name: Configure web servers
  hosts: webservers
  become: true
  gather_facts: true

  tasks:
    - name: Install Nginx
      ansible.builtin.package:
        name: nginx
        state: present

    - name: Start Nginx
      ansible.builtin.service:
        name: nginx
        state: started
        enabled: true
```

## Execute

```bash
ansible-playbook site.yml
ansible-playbook -i inventory.ini site.yml
ansible-playbook site.yml --check
ansible-playbook site.yml --check --diff
ansible-playbook site.yml --limit webservers
ansible-playbook site.yml --tags configuration
ansible-playbook site.yml --skip-tags packages
```

## Validate

```bash
ansible-playbook site.yml --syntax-check
ansible-playbook site.yml --list-hosts
ansible-playbook site.yml --list-tasks
ansible-playbook site.yml --list-tags
ansible-lint site.yml
```

## Task Control

```yaml
- name: Install package on Debian systems
  ansible.builtin.apt:
    name: nginx
    state: present
  when: ansible_facts.os_family == 'Debian'
  tags:
    - packages
```

## Rolling Execution

```yaml
- name: Rolling deployment
  hosts: webservers
  serial: 2
  max_fail_percentage: 25
  tasks:
    - name: Deploy application
      ansible.builtin.debug:
        msg: Deploying {{ inventory_hostname }}
```

# Ansible : Ad Hoc Commands

## Connectivity

```bash
ansible all -i inventory.ini -m ansible.builtin.ping
ansible webservers -m ansible.builtin.setup
ansible all -m ansible.builtin.command -a 'uptime'
```

## Command and Shell

```bash
ansible all -m ansible.builtin.command -a 'uname -a'
ansible all -m ansible.builtin.shell -a 'df -h | sort'
ansible all -m ansible.builtin.raw -a 'python3 --version'
```

Prefer `command` when shell operators, expansions and pipelines are unnecessary.

## Files

```bash
ansible webservers -m ansible.builtin.copy   -a 'src=./app.conf dest=/etc/app.conf owner=root group=root mode=0644'   --become

ansible webservers -m ansible.builtin.file   -a 'path=/srv/app state=directory owner=deploy group=deploy mode=0755'   --become
```

## Packages and Services

```bash
ansible webservers -m ansible.builtin.package   -a 'name=nginx state=present' --become

ansible webservers -m ansible.builtin.service   -a 'name=nginx state=restarted enabled=true' --become
```

## Limits and Check Mode

```bash
ansible all -m ansible.builtin.ping --limit web1.example.com
ansible webservers -m ansible.builtin.package   -a 'name=nginx state=present' --check --become
```

# Ansible : Inventory

## INI Inventory

```ini
[webservers]
web1.example.com ansible_user=deploy
web2.example.com ansible_user=deploy

[databases]
db1.example.com ansible_user=postgres

[production:children]
webservers
databases

[production:vars]
ansible_python_interpreter=/usr/bin/python3
environment=production
```

## YAML Inventory

```yaml
all:
  children:
    webservers:
      hosts:
        web1.example.com:
          ansible_user: deploy
        web2.example.com:
          ansible_user: deploy
    databases:
      hosts:
        db1.example.com:
          ansible_user: postgres
  vars:
    ansible_python_interpreter: /usr/bin/python3
```

## Inspect Inventory

```bash
ansible-inventory -i inventory.ini --graph
ansible-inventory -i inventory.ini --list
ansible-inventory -i inventory.ini --host web1.example.com
ansible all -i inventory.ini --list-hosts
ansible webservers -i inventory.ini --list-hosts
```

## Patterns

```bash
ansible all --list-hosts
ansible webservers --list-hosts
ansible 'webservers:&production' --list-hosts
ansible 'production:!databases' --list-hosts
ansible 'webservers[0]' --list-hosts
```

## Inventory Variables

```text
group_vars/all.yml
group_vars/webservers.yml
host_vars/web1.example.com.yml
```

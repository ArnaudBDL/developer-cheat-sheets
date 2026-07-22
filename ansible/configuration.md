# Ansible : Configuration

## Configuration Precedence

```text
ANSIBLE_CONFIG environment variable
./ansible.cfg
~/.ansible.cfg
/etc/ansible/ansible.cfg
```

## Basic ansible.cfg

```ini
[defaults]
inventory = ./inventory.ini
roles_path = ./roles
collections_path = ./collections
forks = 10
timeout = 30
host_key_checking = True
retry_files_enabled = False
stdout_callback = default
interpreter_python = auto_silent

[privilege_escalation]
become = False
become_method = sudo
become_ask_pass = False

[ssh_connection]
pipelining = True
ssh_args = -o ControlMaster=auto -o ControlPersist=60s
```

## Inspect Configuration

```bash
ansible-config view
ansible-config dump
ansible-config dump --only-changed
ansible-config list
ansible-config init --disabled > ansible.cfg
```

## Environment Variables

```bash
export ANSIBLE_CONFIG="$PWD/ansible.cfg"
export ANSIBLE_INVENTORY="$PWD/inventory.ini"
export ANSIBLE_FORKS=20
export ANSIBLE_STDOUT_CALLBACK=default
```

## Validate Project Configuration

```bash
ansible-config dump --only-changed
ansible-inventory --graph
ansible all -m ansible.builtin.ping
```

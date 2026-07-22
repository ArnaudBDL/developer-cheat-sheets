# Ansible : Roles

## Create a Role

```bash
ansible-galaxy role init roles/webserver
ansible-galaxy role list
```

## Role Structure

```text
roles/webserver/
├── defaults/main.yml
├── files/
├── handlers/main.yml
├── meta/main.yml
├── tasks/main.yml
├── templates/
├── tests/
└── vars/main.yml
```

## Use a Role

```yaml
- name: Configure web servers
  hosts: webservers
  become: true
  roles:
    - role: webserver
      vars:
        webserver_port: 8080
```

## include_role and import_role

```yaml
- name: Include a role dynamically
  ansible.builtin.include_role:
    name: webserver
  when: webserver_enabled | bool

- name: Import a role statically
  ansible.builtin.import_role:
    name: baseline
```

## Role Dependencies

```yaml
# roles/webserver/meta/main.yml
dependencies:
  - role: baseline
  - role: firewall
    vars:
      allowed_ports:
        - 80
        - 443
```

## Install External Roles

```yaml
# requirements.yml
roles:
  - name: geerlingguy.nginx
    version: 3.2.0
```

```bash
ansible-galaxy role install -r requirements.yml
```

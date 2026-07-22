# Ansible : Variables

## Play Variables

```yaml
- name: Configure application
  hosts: application
  vars:
    application_port: 8080
    application_environment: production
  tasks:
    - name: Display configuration
      ansible.builtin.debug:
        msg: "{{ application_environment }}:{{ application_port }}"
```

## Variable Files

```yaml
vars_files:
  - vars/common.yml
  - "vars/{{ environment }}.yml"
```

## Inventory Variables

```yaml
# group_vars/all.yml
ntp_servers:
  - time.cloudflare.com
  - time.google.com

# host_vars/web1.example.com.yml
application_port: 8081
```

## Default Values

```yaml
application_port: "{{ configured_port | default(8080) }}"
required_value: "{{ secret_value | mandatory }}"
```

## Registered Variables

```yaml
- name: Read service status
  ansible.builtin.command: systemctl is-active nginx
  register: nginx_status
  changed_when: false
  failed_when: nginx_status.rc not in [0, 3]

- name: Display status
  ansible.builtin.debug:
    var: nginx_status.stdout
```

## Extra Variables

```bash
ansible-playbook site.yml -e environment=staging
ansible-playbook site.yml -e @vars/production.yml
ansible-playbook site.yml -e '{"replicas":3}'
```

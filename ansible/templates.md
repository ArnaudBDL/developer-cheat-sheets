# Ansible : Templates

## Template Task

```yaml
- name: Deploy application configuration
  ansible.builtin.template:
    src: application.conf.j2
    dest: /etc/application/application.conf
    owner: root
    group: root
    mode: '0644'
    validate: '/usr/bin/application --check-config %s'
  notify: Restart application
```

## Jinja2 Template

```jinja2
# Managed by Ansible
server_name = {{ inventory_hostname }}
port = {{ application_port | default(8080) }}
environment = {{ application_environment }}

{% for host in groups['webservers'] %}
backend = {{ hostvars[host].ansible_host | default(host) }}
{% endfor %}
```

## Conditionals

```jinja2
{% if tls_enabled | bool %}
tls = true
certificate = {{ certificate_path }}
{% else %}
tls = false
{% endif %}
```

## Useful Filters

```jinja2
{{ value | default('fallback') }}
{{ enabled | bool }}
{{ items | join(',') }}
{{ data | to_nice_json }}
{{ data | to_nice_yaml }}
{{ password | password_hash('sha512') }}
```

## Template Lookup

```yaml
- name: Render content locally
  ansible.builtin.set_fact:
    rendered_content: "{{ lookup('ansible.builtin.template', 'message.j2') }}"
```

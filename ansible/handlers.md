# Ansible : Handlers

## Notify a Handler

```yaml
tasks:
  - name: Deploy Nginx configuration
    ansible.builtin.template:
      src: nginx.conf.j2
      dest: /etc/nginx/nginx.conf
      mode: '0644'
    notify: Reload Nginx

handlers:
  - name: Reload Nginx
    ansible.builtin.service:
      name: nginx
      state: reloaded
```

## Multiple Notifications

```yaml
notify:
  - Validate application
  - Restart application
```

## listen

```yaml
handlers:
  - name: Reload web server
    ansible.builtin.service:
      name: nginx
      state: reloaded
    listen: Restart web stack

  - name: Restart application
    ansible.builtin.service:
      name: application
      state: restarted
    listen: Restart web stack
```

## Flush Handlers

```yaml
- name: Run pending handlers now
  ansible.builtin.meta: flush_handlers
```

Handlers run only when notified by a changed task and normally execute at the end of the relevant play section.

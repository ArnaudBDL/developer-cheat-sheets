# Ansible : Vault

## Create and Edit

```bash
ansible-vault create group_vars/production/vault.yml
ansible-vault edit group_vars/production/vault.yml
ansible-vault view group_vars/production/vault.yml
```

## Encrypt and Decrypt

```bash
ansible-vault encrypt secrets.yml
ansible-vault decrypt secrets.yml
ansible-vault rekey secrets.yml
```

## Encrypt a Single Value

```bash
ansible-vault encrypt_string --name database_password
ansible-vault encrypt_string 'change-me' --name database_password
```

## Run Playbooks

```bash
ansible-playbook site.yml --ask-vault-pass
ansible-playbook site.yml --vault-password-file .vault-password
ansible-playbook site.yml --vault-id production@prompt
ansible-playbook site.yml --vault-id production@.vault-production
```

## Use Encrypted Variables

```yaml
vars_files:
  - group_vars/production/vault.yml

tasks:
  - name: Use secret without displaying it
    ansible.builtin.template:
      src: application.conf.j2
      dest: /etc/application/application.conf
      mode: '0600'
    no_log: true
```

## Security Rules

- Do not commit vault password files.
- Restrict access to vault identities and password sources.
- Use `no_log: true` for tasks that may expose secrets.
- Rotate secrets independently from vault-password changes.
- Remember that decrypted content can still appear in processes, temporary files or logs.

# Ansible : Quick References

## Inventory

```bash
ansible-inventory -i inventory.ini --graph
ansible all -i inventory.ini --list-hosts
ansible all -i inventory.ini -m ping
```

## Playbooks

```bash
ansible-playbook -i inventory.ini playbook.yml
ansible-playbook -i inventory.ini playbook.yml --check
ansible-playbook -i inventory.ini playbook.yml --diff
ansible-playbook -i inventory.ini playbook.yml --tags deploy
```

## Vault

```bash
ansible-vault create secrets.yml
ansible-vault edit secrets.yml
ansible-vault encrypt secrets.yml
ansible-vault decrypt secrets.yml
```

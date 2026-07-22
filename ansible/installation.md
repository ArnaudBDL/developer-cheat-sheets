# Ansible : Installation

## pipx

```bash
pipx install --include-deps ansible
pipx upgrade ansible
ansible --version
```

## Python Virtual Environment

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
python -m pip install ansible
ansible --version
```

## Package Managers

```bash
# macOS
brew install ansible

# Debian / Ubuntu
sudo apt update
sudo apt install ansible

# Fedora
sudo dnf install ansible
```

## Verify Commands

```bash
ansible --version
ansible-playbook --version
ansible-config --version
ansible-galaxy --version
ansible-vault --version
```

## Install Collections

```bash
ansible-galaxy collection install community.general
ansible-galaxy collection list
ansible-galaxy collection install -r requirements.yml
```

## SSH Prerequisites

```bash
ssh-keygen -t ed25519
ssh-copy-id user@host
ssh user@host
ansible all -i inventory.ini -m ansible.builtin.ping
```

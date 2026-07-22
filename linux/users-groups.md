# Linux : Users and Groups

## Inspect Identity

```bash
whoami
id
id username
groups
groups username
getent passwd username
getent group groupname
```

## Create and Modify Users

```bash
sudo useradd --create-home --shell /bin/bash alice
sudo passwd alice
sudo usermod --append --groups developers alice
sudo usermod --shell /bin/bash alice
sudo userdel --remove alice
```

## Manage Groups

```bash
sudo groupadd developers
sudo groupmod --new-name engineering developers
sudo gpasswd --add alice developers
sudo gpasswd --delete alice developers
sudo groupdel engineering
```

## Sessions

```bash
who
w
last
lastlog
loginctl list-sessions
```

## Privilege Escalation

```bash
sudo command
sudo -u username command
sudo -i
sudo visudo
sudo -l
```

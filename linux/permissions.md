# Linux : Permissions

## Permission Model

```text
r  Read
w  Write
x  Execute or traverse
u  Owner
g  Group
o  Others
a  All classes
```

## Inspect

```bash
ls -l file.txt
stat file.txt
namei -l /path/to/file
getfacl file.txt
```

## Change Permissions

```bash
chmod 644 file.txt
chmod 755 script.sh
chmod u+x script.sh
chmod go-rwx secret.txt
chmod -R u=rwX,g=rX,o= directory/
```

## Ownership

```bash
sudo chown user file.txt
sudo chown user:group file.txt
sudo chown -R user:group directory/
sudo chgrp group file.txt
```

## Default Permissions

```bash
umask
umask 027
```

## ACL

```bash
setfacl -m u:alice:rw file.txt
setfacl -m g:developers:rX directory/
setfacl -x u:alice file.txt
getfacl file.txt
```

## Special Bits

```bash
chmod u+s executable
chmod g+s shared-directory
chmod +t shared-directory
```

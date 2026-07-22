# Linux : Quick References

## Files

```bash
ls -lah
pwd
find . -type f -name "*.log"
grep -RIn "pattern" .
cp -a source destination
mv source destination
rm -rf path
```

## Processes and services

```bash
ps aux
top
kill PID
systemctl status SERVICE
systemctl restart SERVICE
journalctl -u SERVICE -f
```

## Permissions

```bash
chmod 755 file
chmod -R u+rwX,g+rX,o-rwx directory
chown -R user:group path
```

## Networking

```bash
ip addr
ip route
ss -tulpn
curl -I URL
ping HOST
traceroute HOST
```

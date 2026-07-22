# Networking : Quick References

## Interfaces and routes

```bash
ip addr show
ip link show
ip route show
ip neigh show
```

## Ports and connections

```bash
ss -tulpn
ss -ant
lsof -i :8080
nc -vz HOST PORT
```

## Diagnostics

```bash
ping HOST
traceroute HOST
mtr HOST
dig HOST
curl -v URL
```

## CIDR reminders

```text
/8   255.0.0.0
/16  255.255.0.0
/24  255.255.255.0
/32  single IPv4 address
```

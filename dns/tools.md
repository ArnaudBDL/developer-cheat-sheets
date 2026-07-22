# DNS : Tools

## dig

```bash
dig example.com
dig example.com A
dig example.com MX
dig +short example.com
dig @SERVER example.com
dig +trace example.com
dig -x 192.0.2.10
dig example.com +tcp
dig example.com +dnssec
```

## host and nslookup

```bash
host example.com
host -t MX example.com
host 192.0.2.10
nslookup example.com
nslookup -type=TXT example.com
```

## Resolver Tools

```bash
getent hosts example.com
resolvectl query example.com
resolvectl status
scutil --dns
ipconfig /displaydns
```

## Authoritative Server Validation

```bash
named-checkconf
named-checkzone example.com /etc/bind/zones/db.example.com
rndc status
rndc reload example.com
```

## DNSSEC Tools

```bash
delv example.com A
dig example.com DNSKEY +dnssec
dig example.com DS +dnssec
dnssec-verify -o example.com signed-zone.db
```

## Packet Capture

```bash
sudo tcpdump -ni any port 53
sudo tcpdump -ni INTERFACE 'udp port 53 or tcp port 53'
sudo tshark -i INTERFACE -f 'port 53'
```

## Connectivity

```bash
nc -vz DNS_SERVER 53
nc -vzu DNS_SERVER 53
```

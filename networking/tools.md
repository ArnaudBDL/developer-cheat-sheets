# Networking : Tools

## Interface and Addressing

```bash
ip link show
ip address show
ip -6 address show
ifconfig
networkctl status
```

## Routes and Neighbors

```bash
ip route show
ip -6 route show
ip route get 203.0.113.10
ip neigh show
arp -an
```

## Sockets

```bash
ss -lntup
ss -tan
lsof -i
```

## Connectivity and Path

```bash
ping -c 4 192.0.2.10
ping -6 -c 4 2001:db8::10
traceroute example.com
tracepath example.com
mtr example.com
```

## DNS and HTTP

```bash
dig example.com
resolvectl query example.com
curl -v https://example.com
curl -I https://example.com
openssl s_client -connect example.com:443 -servername example.com
```

## Packet Capture and Scanning

```bash
sudo tcpdump -ni any host 192.0.2.10
sudo tcpdump -ni eth0 port 53
sudo tshark -i eth0
nmap -sT -p 22,80,443 192.0.2.10
nc -vz example.com 443
```

Use packet capture and scanning only on networks and systems you are authorized to test. Captures can contain credentials or sensitive application data.

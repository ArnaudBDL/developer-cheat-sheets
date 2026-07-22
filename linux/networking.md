# Linux : Networking

## Interfaces and Addresses

```bash
ip address
ip link
ip -brief address
ip route
ip neigh
```

## Connectivity

```bash
ping -c 4 example.com
tracepath example.com
traceroute example.com
curl -I https://example.com
nc -vz example.com 443
```

## DNS

```bash
resolvectl status
resolvectl query example.com
dig example.com
getent hosts example.com
cat /etc/resolv.conf
```

## Listening Ports and Connections

```bash
ss -lntup
ss -tnp
sudo lsof -nP -iTCP -sTCP:LISTEN
```

## NetworkManager

```bash
nmcli device status
nmcli connection show
nmcli device wifi list
nmcli connection up CONNECTION
```

## Packet Capture

```bash
sudo tcpdump -ni any
sudo tcpdump -ni INTERFACE host HOST
sudo tcpdump -ni INTERFACE port 443
```

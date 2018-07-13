
# Answer

NATするときに必要

```
sysctl -w net.ipv4.ip_forward=1
```

REDIRECT使った版

```
iptables -t nat -A PREROUTING -i nat1 -p tcp --dport 443 -j REDIRECT --to-port 22022
```

DNAT

```
iptables -t nat -A PREROUTING -i nat1 -p tcp --dport 443 -j DNAT --to-destination 10.0.0.1:22022
```

永続化させるなら

```
apt install iptables-persistent
/etc/init.d/netfilter-persistent save
```


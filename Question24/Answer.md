
# Answer

IPを `getent hosts net-exam-2` で確認(ここでは 192.168.56.103 とする)

`charles` のuidを確認(ここでは 1001 とする)

iptablesを設定

```
iptables -A OUTPUT -p tcp -d 192.168.56.103 --dport 432 -m owner --uid-owner 1001 -j REJECT
```

マシンが自分自身だったら `loopback` も設定

```
iptables -A OUTPUT -p tcp -d 127.0.0.1 --dport 432 -m owner --uid-owner 1001 -j REJECT
```



# Answer

`net-exam-3` で `getent hosts net-exam-1` を実行してIPアドレスを取得(ここでは `192.168.10.2` とする)

iptablesを設定

```
iptables -A INPUT -s 192.168.10.2 -p tcp --dport 6789 -m state --state NEW -j ACCEPT
iptables -A INPUT -p tcp -m state --state NEW -j DROP
iptables -A INPUT -p udp -j DROP
iptables -A FORWARD -s 192.168.10.2 -p tcp --dport 6789 -m state --state NEW -j ACCEPT
iptables -A FORWARD -p tcp -m state --state NEW -j DROP
iptables -A FORWARD -p udp -j DROP
iptables -A OUTPUT -d 192.168.10.2 -p tcp -m state --state NEW -j DROP
iptables -A OUTPUT -d 192.168.10.2 -p udp -j DROP
```

永続化させるなら

```
apt install iptables-persistent
/etc/init.d/netfilter-persistent save
```



# Answer

```sh
apt install rsyslog
```

をやって以下２行をアンコメントしてポートを指定

```
module(load="imudp")
input(type="imudp" port="9514")
```

そしてRestart

```sh
systemctl restart rsyslog
```


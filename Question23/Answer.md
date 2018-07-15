
# Answer

`Squid` をインストール

```
apt install squid
```

`getent hosts app-0` でIPを取得する(ここでは `192.168.56.102` とする)

`/etc/squid/squid.conf` を部分的に編集(cache_peerのポートは要確認)

```
http_port 8164 accel defaultsite=localhost

cache_peer 192.168.56.102 parent 8164 0 no-query originserver
```

`squid` のStartとEnable

```
systemctl start squid
systemctl enable squid
```


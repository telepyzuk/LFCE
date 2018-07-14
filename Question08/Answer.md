
# Answer

bindをインストール、自動起動するように設定し起動

```
apt install bind9
systemctl enable bind9
systemctl start bind9
```

loopbackはListenさせろとのことなので `named.conf.options` 一応追記しておく

```
listen-on { any; };
```

`/etc/bind/zones` フォルダを作る

```
mkdir -p /etc/bind/zones
```

`internal` 用のzoneを用意する

```
$ORIGIN example.info.
$TTL 86400
@       IN SOA    dns1.example.info. postmaster.example.info. (
        2012022207      ; Serial
        10800           ; Refresh
        3600            ; Retry
        3600000         ; Expire
        3600            ; Negative Cashe TTL
)

        IN NS    dns1.example.info.
dns1    IN A     192.168.23.10 ; FIXME
webdev  IN A     192.168.23.85
```

`external` 用のzoneを用意する

```
$ORIGIN example.info.
$TTL 86400
@       IN SOA    dns1.example.info. postmaster.example.info. (
        2012022207      ; Serial
        10800           ; Refresh
        3600            ; Retry
        3600000         ; Expire
        3600            ; Negative Cashe TTL
)

        IN NS    dns1.example.info.
dns1    IN A     192.0.2.10 ; FIXME
webdev  IN A     192.0.2.243
```

`internal` と `external` を切り替えるviewを `/etc/bind/named.conf.local` に設定

```
view "internal" {
        match-clients { 10.250.0.0/24; };
        recursion yes;

        include "/etc/bind/named.conf.default-zones";

        zone "example.info" {
                type master;
                file "/etc/bind/zones/example.info-internal.db";
        };
};

view "external" {
        match-clients { any; };
        recursion no;

        zone "example.info" {
                type master;
                file "/etc/bind/zones/example.info-external.db";
        };
};
```

`/etc/bind/named.conf.default-zones` を `/etc/bind/named.conf` からコメントアウト

```
include "/etc/bind/named.conf.options";
include "/etc/bind/named.conf.local";
//include "/etc/bind/named.conf.default-zones";
```


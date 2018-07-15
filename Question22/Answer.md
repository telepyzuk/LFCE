
# Answer

`postfix` をインストール

```
apt install postfix
```

`c.tux.rocks` をリレーするように `main.cf` を設定

```
relay_domains = c.tux.rocks
```

access listを `/etc/postfix/access` に作成

```
example.net REJECT
example.com OK
```

インデックスファイルを作成

```
postmap /etc/postfix/access
```

`main.cf` にリストをチェックするように設定を追記

```
smtpd_sender_restrictions = check_sender_access hash:/etc/postfix/access
```


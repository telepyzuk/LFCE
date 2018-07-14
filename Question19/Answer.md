
# Answer

`prod_pk.key` を使ってcsrを作成。適宜情報を入力

```
openssl req -new -key /opt/CESC00101/ssl/prod_pk.key > /opt/CESC00101/ssl/srv.csr
```

`prod_pk.key` と `srv.csr` を使ってcrtを作成

```
openssl x509 -days 730 -req -signkey /opt/CESC00101/ssl/prod_pk.key < /opt/CESC00101/ssl/srv.csr > /opt/CESC00101/ssl/ca.crt
```

作った証明書を配置

```
mkdir -p /etc/pki/tls/{certs,private}
cp /opt/CESC00101/ssl/ca.crt /etc/pki/tls/certs/
cp /opt/CESC00101/ssl/srv.csr /etc/pki/tls/private/
cp /opt/CESC00101/ssl/prod_pk.key /etc/pki/tls/private/
```

Webサーバーを入れる(nginx)

```
apt install nginx
```

`/etc/nginx/site-available/default` をコピー

```
cp /etc/nginx/site-available/default{,-ssl}
```

`/etc/nginx/site-available/default` を編集

```
listen 799 default_server;
listen [::]:799 default_server;
server_name app.example.com;
```

`/etc/nginx/site-available/default-ssl` を編集

```
listen 8993 ssl;
listen [::]:8993 ssl;
server_name app.example.com;

ssl on;
ssl_certificate      /etc/pki/tls/certs/ca.crt;
ssl_certificate_key  /etc/pki/tls/private/prod_pk.key;
```

`default-ssl` を有効化

```
ln -s /etc/nginx/sites-available/default-ssl /etc/nginx/sites-enabled/default-ssl
```


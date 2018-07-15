
# Answer

Sambaをインストール

```
apt install samba
```

共有するディレクトリの作成

```
mkdir -p /opt/sharelinux
```

設定ファイル `/etc/samba/smb.conf` を編集

```
[Sharesmith]
    path = /opt/sharelinux
    writable = yes
    guest ok = no
    create mode = 0700
    directory mode = 0664
    write list = robert
```

`robert` ユーザを作成

```
useradd -m robert
pdbedit -a robert
```

smb再起動とEnable

```
systemctl restart smbd
systemctl enable smbd
```

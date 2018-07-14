
# Answer


`/nfs/share3` を `NFSv4` で共有

`10.1.1.0/22` をread-onlyでInsecureShare
`example.org` をSecureShare

rootでのアクセスはAnonymousとしてログインさせる

ファイルの作成は644、フォルダの作成は775とする


nfsサーバーを必要だったらインストール

```
apt install nfs-kernel-server
```

`/etc/exports` を編集

```
/nfs/share3 10.1.1.0/22(ro,insecure,root_squash) example.org(rw,secure,root_squash)
```

`umask` 変更のため `setfacl` を 実行

```
setfacl -d -R --set u::rwx,g::rwx,o::r-x /nfs/share3
```


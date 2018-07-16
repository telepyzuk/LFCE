
# Answer

`FinanceFE` の確認

```
lxc-ls -f
```

コピーする

```
lxc-copy -n FinanceFE -N testly -p /srv/lxc
```

自動起動については `/var/lib/lxc/${コンテナ名}/config` で以下のパラメータを確認

```
lxc.start.auto = 1
```

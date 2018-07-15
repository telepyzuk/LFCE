
# Answer

これについてはなんとも言えず・・。

Apparmorの設定ファイルは `/etc/apparmor.d` 下に保存されている。

中身はこんな感じ？

```
#include <tunables/global>

profile mysqld /usr/sbin/mysqld {
    #include <abstractions/base>

    /usr/sbin/mysqld rm,

    /var/lib/mysql/ r,
    /var/lib/mysql/** rw,

    /var/run/mysqld/ r,
    /var/run/mysqld/mysqld.sock rw,
}
```

でどうやらSocketが作成できなかった感じがあるので、作成できる権限にすればいいと思う

# Information

## Profile の作成手順

utilsを入れる

```
apt install apparmor-utils
```

Profileを作る

```
aa-genprof /to/process
```

Complainモードにする

```
aa-complain /etc/apparmor.d/to.process
```

適当にプログラム動かしてから `aa-logprof` でルールを追加していく

```
aa-logprof
```

Enforceモードにもどす

```
aa-enforce /etc/apparmor.d/to.process
```

## 権限について

- `r` : Read
- `w` : Write
- `m` : Memory map executable
- `x` : Execute



# Answer

これはどうも `/etc/pam_vars.conf` が提供されていることが期待できる

なかったら以下を作る

```
JAVA_HOME   DEFAULT=/usr/local/java1.8
USERNAME    DEFAULT=nobody      OVERRIDE=@{PAM_USER}
HOSTNAME    DEFAULT=localhost   OVERRIDE=@{PAM_RHOST}
WHOAMI      DEFAULT=${USERNAME}\@${HOSTNAME}
```

`/etc/pam.d/sshd` に追記

```
session    required     pam_env.so conffile=/etc/pam_vars.conf
```


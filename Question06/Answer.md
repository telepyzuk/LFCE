
# Answer

`/etc/pam.d/login` に `pam_tally2` を追加

```
auth     required       pam_securetty.so
auth     required       pam_tally2.so deny=5 even_deny_root
```

ついでにSSHに `UsePAM` が `yes` になっているかも確認


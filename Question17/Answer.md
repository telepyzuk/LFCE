
# Answer

以下を実行(パッケージ名を `kernel.deb` としている)

```
dpkg -i /srv/kernel.deb
```

`grub.cfg` を作成する

```
grub-mkconfig -o /boot/grub/grub.cfg
```

`/boot/grub/grub.cfg` の `menuentry` をみてブートさせるkernelを選び、 `grub-set-default` で設定

```
grub-set-default new-kernel
```

rebootして確認


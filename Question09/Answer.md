
# Answer

デバイスの情報を取得

```
udevadm info -a -p $(udevadm info -q path -n /dev/xvdw1)
```


表示された情報をもとに、デバイスのルールファイルを `/etc/udev/rules.d/85-prod_data.rules` に作成

```
KERNEL=="sda1", SYMLINK+="prod_data"
```

リロードして確認してみる

```
udevadm trigger
```


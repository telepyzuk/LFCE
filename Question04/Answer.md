
# Answer

`vg2` の作成

```
vgcreate -s 5m vg2 /dev/xvdt1 /dev/xvdt2 /dev/xvdt3
```

`stripedVol3` の作成

```
lvcreate -L 30m -i 3 -I 64 -n stripedVol3 vg2
```

`mirroredVol1` の作成

```
lvcreate -m2 -L 32m -n mirroredVol1 vg1
```

`linearVol2` の拡張

```
lvextend -L 12m /dev/vg1/linearVol2
```

# Infomation

partedのパーティション作成

```
parted /dev/sdb
p
unit MiB
mklabel gpt
mkpart P1 ext4 0 1024
p
quit
```


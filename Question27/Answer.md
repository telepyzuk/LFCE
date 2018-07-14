
# Answer

Serviceを追加

```
ipvsadm -A -t 10.10.73.22:443 -s sh
```

Serverを追加

```
ipvsadm -a -t 10.10.73.22:443 -r net-app-0:7644
ipvsadm -a -t 10.10.73.22:443 -r net-app-1:7644
```


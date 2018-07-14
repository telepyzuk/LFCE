
# Answer

カーネルパラメータを変更

```
sysctl -w vm.nr_hugepages=8
sysctl -w vm.overcommit_memory=1
sysctl -w vm.overcommit_ratio=45
sysctl -w vm.hugetlb_shm_group=201
```


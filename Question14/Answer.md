
# Answer

`/opt/CESD00501/domain.xml` の要素をよしなに編集

```
<domain type='lxc'>
  <name>cloudx-dev</name>
  <vcpu>1</vcpu>
  <memory unit='MiB'>512</memory>
  <devices>
    <interface type='network'>
      <source network='br0'>
    </interface>
  </devices>
</domain>
```


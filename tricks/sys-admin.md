---
autho: mkx
---

## hibernate
```bash
cd
sudo ./.hibernate.sh
```


## print $PATH line by line
```bash
# tr command
echo $PATH | tr : '\n'
# or substitution
echo -e ${PATH//:/\\n}
```

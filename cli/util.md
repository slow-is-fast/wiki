# Utils

## Alias

###打开每日issue
```shell
alias td="cd {local_repo};hub browse -- issues/`hub issue -L 1  | cut -d ' '  -f 5 | sed 's/#//'`; cd -"
alias daily="hub issue  create -l 'AUTO' -l `date +%Y%m` -m `date +%Y-%m-%d` -a slow-is-fast -M `date +%Y-%m`"
```

### 按文件后缀统计文件数量

count files by its extension name.

```shell
alias ce='find . -type f | rev | cut -d. -f1 | rev  | sort | uniq -c'
```
# Utils

## Alias

### ~~打开每日issue~~
```shell
alias td="cd {local_repo};hub browse -- issues/`hub issue -L 1  | cut -d ' '  -f 5 | sed 's/#//'`; cd -"
alias daily="hub issue  create -l 'AUTO' -l `date +%Y%m` -m `date +%Y-%m-%d` -a slow-is-fast -M `date +%Y-%m`"
```

### 打开每日issue
function td () {
    ( cd {YOUR LOCAL REPO} && hub browse -- issues/`hub issue -L 1  | cut -d ' '  -f 5 | sed 's/#//'`  )
}

function da () {
    ( cd {YOUR LOCAL REPO} && hub issue create -l 'AUTO' -l `date +%Y%m` -m `date +%Y-%m-%d` -a slow-is-fast -M `date +%Y-%m` )
}

### 按文件后缀统计文件数量

count files by its extension name.

```shell
alias ce='find . -type f | rev | cut -d. -f1 | rev  | sort | uniq -c'
```


## Scripts


### 批量打开URL
``` shell
cat links.txt | while read line
do
    echo $line;
    open $line -a "/Applications/Safari.app"
    sleep 5;
done
```

```text
https://example.com/url_1
https://example.com/url_2
https://example.com/url_3
https://example.com/url_4


```


有个小问题，links.txt如果没有最后一个空行，不会打开最后一个URL。
还没找到原因
























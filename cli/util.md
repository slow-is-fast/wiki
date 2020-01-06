# Utils

## Alias

### ~~打开每日issue~~
需要安装github cli 客户端hub


```shell
alias td="cd {local_repo};hub browse -- issues/`hub issue -L 1  | cut -d ' '  -f 5 | sed 's/#//'`; cd -"
alias daily="hub issue  create -l 'AUTO' -l `date +%Y%m` -m `date +%Y-%m-%d` -a slow-is-fast -M `date +%Y-%m`"
```

### 打开每日issue

需要安装github cli 客户端hub

```shell
function td () {
    ( cd {YOUR LOCAL REPO} && hub browse -- issues/`hub issue -L 1  | cut -d ' '  -f 5 | sed 's/#//'`  )
}

function da () {
    ( cd {YOUR LOCAL REPO} && hub issue create -l 'AUTO' -l `date +%Y%m` -m `date +%Y-%m-%d` -a slow-is-fast -M `date +%Y-%m` )
}
```

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


### 批量转换文件编码

```shell
iconv -l
```
显示iconv支持的编码格式


```shell
find . -type f -exec iconv -f GBK -t UTF8 {}  > {}_utf.html \;
```
一开始想到的是这种方法,
可是全部的输出都重定向到了一个名字真的叫 {}_utf.html 的文件。
失败
遂尝试写for循环来处理


#### 所有要转换的文件都在当前目录里
```shell
for f in *.html; do iconv -c -f GBK -t UTF8 $f > $f.utf.html; done
```


#### 所有要转换的文件都在一个独立的子目录里

```shell
for f in */*.html; do 
iconv -c -f GBK -t UTF8 $f > $f.utf.html;
done
```




### 统计git log中新增/删除代码行数 


```shell
git log --author="$(git config --get user.name)" --no-merges --since=2018-01-01 --until=2021-01-01  --pretty=tformat: --numstat | awk '{ add += $1 ; subs += $2 ; loc += $1 - $2 } END { printf "added lines: %s removed lines : %s total lines: %s\n",add,subs,loc }'
```


> added lines: 20070 removed lines : 6303 total lines: 13767
















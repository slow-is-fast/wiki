# CLI

## Find

## Date

获取明天的日期 , 
> date -d "tomorrow" +"%Y-%m-%d"

-d "tomorrow "  只有GNU/date可以使用，mac的date命令没有这个选项

+"%Y-%m-%d"  定义日期的输出格式


## Trim String

- 去掉所有空白符
```shell
tr -d '[:space:]'
```

- 去掉前置空格
```shell
sed -e 's/^[[:space:]]*//'
```


## Reference

- [CLI: improved](https://remysharp.com/2018/08/23/cli-improved)





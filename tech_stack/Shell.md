# Alias

# Basics


## Number comparison
```shell
#!/bin/bash

a=2462620;
b=2462620;

if [ "$a" -eq "$b" ];then
  echo "They're equal";
fi
```

## Math

### Add two numbers
(( )) 表达式，用来求值。

```shell
ID=1;
ID=$((ID + 100));
ehco $ID;
```


### 求模数
```shell
if [[ $((ID % 1000)) == 0 ]]; then
    #statements
    echo 'sleep';
fi
```
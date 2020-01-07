# Laravel

## 创建Mysql View和 model class 
###  创建migration
```shell
a make:migration create_point_views
```

```php
DB::statement("create view member_points as (select * from ...");
```

不能再直接使用Schema::create了。


### 直接创建model 就可以
```shell
    a make:model ModelName
```

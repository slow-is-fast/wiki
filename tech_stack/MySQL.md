# MySQL


## 分批备份数据
```sql
mysqldump --opt --where="1 limit 1000000 offset 1000000" --no-create-info database table > table.sql
```

## 查询数据库占用磁盘大小
```sql
select table_schema, sum((data_length+index_length)/1024/1024) AS MB from information_schema.tables group by 1;
```


## 查询表占用磁盘大小


```sql
SELECT table_name AS `Table`, round(((data_length + index_length) / 1024 / 1024), 2) `Size (MB)` FROM information_schema.TABLES WHERE table_schema = "$your_database";
```
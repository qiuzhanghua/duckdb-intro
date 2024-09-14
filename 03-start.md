# Start

### 1. 打开 vscode

### 2. 在 vscode 中新建终端

### 3. 打开一个 DuckDB 数据库

```bash
duckdb sample.duckdb
```

### 4. 查看版本

```sql
select version();
```

### 5. 创建表

```sql
create or replace table ducks as
select 3 as age,
  'yellow' as color;
```

### 6. 从表查询数据

```sql
select * from ducks;
```

### 7. 查看表

```sql
show tables;
```

...

### 10. 关闭数据库

```sql
.exit
```

[DuckDB 扩展](04-extensions.md) | [返回](README.md)

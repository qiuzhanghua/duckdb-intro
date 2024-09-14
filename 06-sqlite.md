# 使用 SQLite

### 1. 打开 vscode

### 2. 在 vscode 中新建终端

### 3. 打开一个 DuckDB 数据库

```bash
duckdb sample.duckdb
```

### 4. 连接 SQLite

```sql
load sqlite;
detach sqlite_db;
ATTACH 'sqlite_file.db' AS sqlite_db (TYPE SQLITE);
show databases;
create or replace table sqlite_db.ducks as select 1 as age,
   'red' as color;
select * from sqlite_db.ducks;
show tables;
```

### 5. csv -> SQLite

```sql
create or replace table sqlite_db.provinces as select * from sample.provinces;
create or replace table sqlite_db.cities as select * from sample.cities;
create or replace table sqlite_db.areas as select * from sample.areas;
create or replace table sqlite_db.streets as select * from sample.streets;
```

### 6. 联合查询 csv 和 SQLite

```sql
select s.name, c.name from streets s
left join sqlite_db.cities as c on s.cityCode = c.code;
```

### 10. 关闭数据库

```sql
.exit
```

[返回](README.md)

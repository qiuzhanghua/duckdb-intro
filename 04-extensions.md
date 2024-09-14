# DuckDB Extensions

### 1. 打开 vscode

### 2. 在 vscode 中新建终端

### 3. 打开一个 DuckDB 数据库

```bash
duckdb sample.duckdb
```

### 4. 查看可以安装的扩展

```sql
select * from duckdb_extensions();
```

### 5. 安装扩展

```sql
install arrow;
install excel;
install fts;
install httpfs;
install iceberg;
install inet;
install mysql;
install postgres;
install spatial;
install sqlite;
install vss;

-- clickhouse
install chsql from community;

```

...

### 10. 关闭数据库

```sql
.exit
```

[分析 csv](05-csv.md) | [返回](README.md)

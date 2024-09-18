# DuckDB Introduction

DuckDB is a fast in-process analytical database.

1.  [安装 DuckDB](01-install.md)
2.  [配置 vscode](02-vscode.md)
3.  [DuckDB 尝鲜](03-start.md)
4.  [DuckDB 扩展](04-extensions.md)
5.  [分析 csv](05-csv.md)
6.  [使用 SQLite](06-sqlite.md)
7.  [使用 PostgreSQL](07-pg.md)
8.  [使用 Python](10-python.md)

## Reference and Thinking

1. [Hydra](https://hydra.so/) 是DuckDB Powered Postgres的云服务，依赖于下面的项目

2. [pg_duckdb](https://github.com/duckdb/pg_duckdb/)是将DuckDB列式存储和其他特性插入PostgreSQL的开源项目，开发中...

3. [MotherDuck](https://motherduck.com/)是适应多云的数据仓库云服务。

4. 已经有ClickHouse的DuckDB extension，https://community-extensions.duckdb.org/extensions/chsql.html

5. Hive，HBase, HDFS等的extensions呢？预计1-2年会有开源出来

6. 数据分析、产品或者项目中可以尝试使用
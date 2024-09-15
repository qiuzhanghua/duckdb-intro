# 使用 Python

### 1. 打开 vscode

### 2. 在 vscode 中新建终端

### 3. 安装 Python 组件

```bash
pip install duckdb pandas polars
```

### 4. 运行 Python

### 5. import

```python
import duckdb
import pandas as pd
```

### 6. 连接 DuckDB

```python
conn = duckdb.connect("sample.duckdb")
# 安装插件
conn.install_extension("spatial")
conn.load_extension("spatial")
```

### 7. 连接与查询

```python
conn.sql("""
create or replace view geo_cities as
select *
from read_csv_auto(
"data/geo/cities.csv",
header = true
);
""")
df = conn.sql("select * from geo_cities")
df.show()
conn.table("geo_cities").show()
```

### 8. GEO 支持

```python
conn.sql('SELECT * FROM ST_Drivers()').show()
```

...

### 10. 关闭数据库，退出 Python

```python
conn.close()
exit()
```

[返回](README.md)

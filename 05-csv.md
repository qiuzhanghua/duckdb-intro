# 分析 CSV

### 1. 打开 vscode

### 2. 在 vscode 中新建终端

### 3. 打开一个 DuckDB 数据库

```bash
duckdb sample.duckdb
```

### 4. 创建视图

```sql
-- data from https://github.com/modood/Administrative-divisions-of-China

-- 省级行政区划代码
create or replace view provinces as
select *
from read_csv_auto(
    "data/china/provinces.csv",
    header = true
  );
-- 市级行政区划代码
create or replace view cities as
select *
from read_csv_auto(
    "data/china/cities.csv",
    header = true
  );
-- 区县级行政区划代码(districts)
create or replace view areas as
select *
from read_csv_auto(
    "data/china/areas.csv",
    header = true
  );
-- 乡镇级行政区划代码(towns)
create or replace view streets as
select *
from read_csv_auto(
    "data/china/streets.csv",
    header = true
  );
-- 村委会级行政区划代码(villages)
create or replace view villages as
select *
from read_csv_auto(
    "data/china/villages.csv",
    header = true
  );
```

### 5. 查询村庄

```sql
select * as count
FROM (
    select p.name as provinceName,
      a.name as areaName,
      c.name as cityName,
      s.name as streetName,
      v.name
    from villages AS v
      LEFT JOIN streets as s ON v.streetCode = s.code
      LEFT JOIN areas as a ON v.areaCode = a.code
      LEFT JOIN cities as c ON v.cityCode = c.code
      LEFT JOIN provinces as p ON v.provinceCode = p.code
  )
limit 5;
-- 查询各省的村数量
select count(*) count,
  p.name
from villages v
  LEFT JOIN provinces as p ON v.provinceCode = p.code
GROUP BY p.name
ORDER BY count DESC;
-- 查询各市的村数量
select count(*) count,
  c.name
from villages v
  LEFT JOIN cities as c ON v.cityCode = c.code
GROUP BY c.name;
```

### 10. 关闭数据库

```sql
.exit
```

[返回](readme.md)

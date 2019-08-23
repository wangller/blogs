- Geometry Accessors 提供要素几何信息的访问
```sql
-- 几何类型
GeometryType(geom): Point, LINESTRING, ... MULTIPOLYGON, GEOMETRYCOLLECTION
ST_GeometryType(geom): ST_Point, ... ST_MultiPolygon, ST_GeometryCollection

-- 几何边界
st_xmin(geom), st_ymin(geom), st_xmax(geom), st_ymax(geom)

-- 查询、设置srid
select st_srid(geom), st_setsrid(geom, 4326) from table;
```

- Management Functions 涉及几何类型列的表结构管理
```sql
-- 添加几何类型的列
select addGeometryColumn('table', 'geom', 4326, 'polygon', 2);
select addGeometryColumn('table', 'geom_coll', 4326, 'GeometryCollection', 2);

-- 删除几何类型的列，没有update
select dropGeometryColumn(table, column);

-- 更新srid
select updateGeometrySRID('table', 'geom', 4326);
```

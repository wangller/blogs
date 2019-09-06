- multipolygon转polygon
```sql
-- 方法1 创建新表
select gid, st_asgeojson((st_dump(geom)).geom::geometry(polygon)) from table;

-- 方法2 coll/mpg/pg代表GeometryCollection/mutilpolygon/polygon类型的列
-- ST_Polygonize(geom_pg)聚合所有geometry为GeometryCollection
update table set geom_coll = (select ST_Polygonize(geom_mpg) from table);
-- ST_GeometryN去第n个
update table set geom_pg = ST_GeometryN(geom_coll, gid);
```
- 坐标转换/投影
```sql
select st_asewkt(st_transform(st_geomfromtext('point (116 39)', 4326), 900913)) geom;
```
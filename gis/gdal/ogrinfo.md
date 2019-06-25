```bash
# 列出gdal支持的文件格式, ESRI Shapefile, GeoJSON ...
ogrinfo --formats

# 该格式支持的option
ogrinfo --format GeoJSON
```

```bash
# 列出其中的图层, shp文件只有一个同名图层
ogrinfo test.shp

# 列出所有layer的所有feature
ogrinfo -al test.shp

# 显示test图层的概要信息(summary only / metadata)
# 如 projection schema feature count extents
ogrinfo -so test.shp test

# 过滤要素, -q和-so相反
# 不显示图层metadata, 不显示geometry字段
ogrinfo -q -where "type=2" -geom=no test.shp test

# 不显示字段值, 简要显示geometry
ogrinfo -geom=summary -fields=no test.shp test
```
- Error performing insert: java.lang.String cannot be cast to org.locationtech.jts.geom.Geometry
```
(1) postgis的table中，geom是MultiPolygon类型，但是前端生成的gml数据是Polygon类型
(2) 使用postgis shapefile loader导入时，默认是MultiPolygon，可以在options中设置
```

- 元素"fj:fj_cities_pg_postgis" 的前缀"fj"未绑定
```
(1) 图层定义的节点，缺失xml命名空间，一般是参数传递不正确
L.wfst参数示例 { typeNS: 'fj', typeName: 'fj_cities_pg_postgis'}

(2) 添加postgis数据源时，有基于工作区(fj)生成的命名空间，如http://geoserver.org/fj
```

- wfs.WFSTransactionException: {http://geoserver.org/fj}fj_cities_pg_postgis is read-only
```
(1) 需要保证geoserver中连接postgis的用户具有编辑权限
(2) geoserver -> Security -> Data中，赋予ROLE_ANONYMOUS角色写权限
```

```bash
# shp转geojson
ogr2ogr -f "geojson" test.geojson test.shp

# geojson转shp
ogr2ogr -f "ESRI Shapefile" test.shp test.geojson
```

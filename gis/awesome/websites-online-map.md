- Google Map（EPSG:3857）的知识
```bash
# 在线地图，金字塔原理
# 经纬度 -> 投影坐标 -> 像素坐标 -> 瓦片坐标的转换过程
# 球面墨卡托投影中，地图级别、分辨率、比例尺的关系
https://www.maptiler.com/google-maps-coordinates-tile-bounds-projection/
```
- ESPG坐标系统查询，坐标投影变换，https://epsg.io

- 空间坐标系统定义查询，https://www.spatialreference.org

- 在线地图经纬度lnglat与瓦片坐标tile之间的计算
```bash
# 谷歌、必应
https://github.com/mapbox/tilebelt

# TMS、谷歌、必应
https://github.com/DenisCarriere/global-mercator

# 谷歌、必应、OSM、高德、腾讯、百度
https://github.com/CntChen/tile-lnglat-transform
```
---
title: Postgis Point in Polygon
date: 2018-08-27T10:47:34.317Z
tags: ["til"]
---
```
drop table if exists tbl ;
create temp table tbl
(
 x polygon
 
);

insert into tbl(x) values ('(0,0),(0,10),(10, 10), (0, 5), (10,0), (0,0)');

select * from tbl where x @>'(5,5)';  --return empty
select * from tbl where x @>'(9.8,9.9)';  --return polygon
```

`@>` = to check point in polygon

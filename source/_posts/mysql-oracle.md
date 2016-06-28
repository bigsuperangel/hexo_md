---
title: mysql与oracle相关函数转化
date: 2016-06-28 10:54:54
tags: [mysql,oracle,database]
---

### 一、日期函数

- mysql

```
str_to_date() 
select str_to_date('2008-4-2 15:3:28','%Y-%m-%d %H:%i:%s');
```

- oracle

```
to_date()
select to_date('2005-01-01 13:14:20','yyyy-MM-dd HH24:mm:ss') from dual; 
```

### 二、聚合函数

- mysql

```
group_concat()
select id,group_concat(name) from aa group by id;
```

- oracle

```
wm_concat()
select aa,wmsys.wm_concat(t1.name) from (
select t.name,to_char(t.createdate,'yyyy-mm-dd') aa from td_user t where t.td_conference_id = 3218 and t.status = 1 and t.createdate > to_date('2012-10-28','yyyy-mm-dd') order by createdate desc
) t1 group by t1.aa 
```



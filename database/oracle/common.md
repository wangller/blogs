#### 使用imp/exp导入导出j
```sql
-- 需要指定owner
exp user_name/pwd@ip:port/orcl owner=user_name tables=(t1, t2, t3) file=g:\output.dmp

-- 导入
imp user_name/pwd@ip:port/orcl file=g:\output.dmp full=y
```
#### 查看建表语句
```sql
-- 查看T1的ddl
select dbms_metadata.get_ddl('TABLE', 'T1') from dual;
```

#### 用table2更新table1
```sql
-- 根据id(有唯一约束的字段)将table2的字段更新到table1
update (select a.f1 a1, a.f2 a2, b.f1 b1, b.f2 b2 
  from table1 a, table2 b where a.id = b.id) 
    set a1 = b1, a2 = b2;
```

#### 启用/禁用触发器
```sql
-- 启用触发器
alter trigger trigger_name enable;

-- 禁用触发器
alter trigger trigger_name disable;
```

#### 利用子查询获取10~20行的记录
```sql
select * from 
  (select t.*,rownum r from test t where rownum <= 20) where r >10;
```

#### 初始登录
```sql
-- 用sys用户登录
-- ORA-28009: connection as SYS should be as SYSDBA or SYSOPER
sqlplus / as sysdba
sqlplus sys/pwd@orcl as sysdba

-- sqlplus中登录
conn / as sysdba

-- 显示当前用户
show user;
```

#### 创建用户(数据库)、用户授权
```sql
-- 创建用户(数据库)
create user user_name identified by pwd;

-- 授予DBA权限
grant dba to user_name;

-- 授予用户选择和删除的权限
grant connect,resource,select,delete on table_name to user_name;
```

#### 数据库重命名
```sql
-- 以sys用户登录
sqlplus / as sysdba

--尝试修改user_name，报错：选项缺失或无效
alter user old_user rename to new_user identified by new_pwd;

--更改系统设置，指定scope=spfile
alter system set "_enable_rename_user"=true scope=spfile;

--以restrict mode重启oracle，可以看一下oracle的启动/关闭过程
shutdown immediate
startup restrict

--再次修改，提示：user is alterd
alter user old_user rename to new_user identified by new_pwd;
```
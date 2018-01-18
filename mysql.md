# 数据库
## 数据库的分类
- 结构化数据库 sql
	- mysql
	- oracle
	- sql server
- 非结构化数据库 nosql
	- redis
	- mongodb
## SQL语句的分类 (strucrtued query language)
- DML 数据库操作语句
	inster, delete, update, alter, drop
- DQL 数据库查询语句
	select
- DDL 数据库定义语句
	create
## database
- show databases; //显示当前主机上所有的数据库
- user database_name; //改变当前选择的数据库
- show create database_name; //显示该数据库创建时使用的命令
- drop database database_name; //删除该数据库
- create database database_name character set utf8 || charset = utf8; //设置数据库字符集
> 校验规则: 数据库字段，值是否区分大小写，和数据排序规则
- show collation //显示当前数据库支持所有校验规则
- create database database_name collate utf8_general_ci; //设置数据库校验规则
- alter database database_name //修改数据库
	-alter database character set utf8; //修改数据库字符集
	-alter database collate collation_name //修改数据库校验规则
## table
- show tables; //显示当前数据库所有表
- show create tables table_name //显示该表创建时使用的语句
- createa
## 数据类型
- 整数类型
	- tinryint
	- int
	- longint
- 浮点数类型
	- float
	- decimer
- 字符串类型
	- char
	- varchar
- 日期类型
	- date
	- datetime
	- time
- set 类型
- enum 类型
- bit 类型
## curd
- create table table_name (colmun_name colmun_desc);
- update table table_name [set] (colmun) = values;
- selcet * from table_name;
- delete from table_name [where];
## 多表查询
	select * from teble_name1, table_name2 where 表的数量-1
## 子查询
	sql语句中的包含的select
## order by 子句
	排序
## group by 子句 分组
	having 过滤
## limit 子句控制显示数量
	### limit 1, 20  从1开始到取20条
## where子句 条件控制
-like匹配 
	- % 任意多个字符
	- _ 任意一个字符
## 系统函数
- 聚合函数
- sum
- avg
- max
- min
- count
- 日期函数
- now
- current_date
- date_sub
- data_add
- unix_timestamp
- 数学函数

## 内连接
	inner join
## 外连接
- 左外连接
	left join
- 右外连接
	right join
## 约束
- 主键约束
	primanry key
- 唯一约束
	unique
- 不可为空约束
	not null
- 外键约束
	foreign key
- check 约束
	check
## 索引
- 主键索引
	primanry key
- 唯一索引
	unique
- 普通索引
	index
- 全文索引
	fulltext
## 事务
- 事务说明
	将一组dml语句看做一个事务，成功则都成功，失败则都失败	
- 事务的特性(acid)
- a 原子性
- c 统一性
- i 隔离性
- d 持久性
- 事务的隔离级别
- 读未提交
- 读已提交
- 可重复读 默认级别
- 可串行化 
> 对当前事务操作的表加锁，其他终端在未释放锁之前不可执行dml语句
- 默认事务的隔离级别 可重复读写
## 存储引擎 engine
- myisam 表的索引，结构，数据反别存放
- innerdb 只存表的结构，数据和索引放在ibdata文件中
- mermory 只存表的结构，数据和索引放在内存中，服务重启则消失
## 视图
	简化sql语句
## 数据库用户管理
- 创建数据库管理用户
- 分配用户权限
- 回收用户权限
## 触发器
## 存储过程
## 自定义函数
## 数据的备份恢复
- 普通备份数据库
- 增量备份
- 备份表
- 从文件中恢复数据库
- 从文件中恢复表
## 数据库的优化
- 慢查询
- 垂直分表
- 水平分表
- 增量备份


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
## 子查询
## order by 子句
## group by 子句
## limit 子句
## where子句
## 系统函数
- 聚合函数
- 日期函数
- 数学函数
## 内连接
## 外连接
- 左外连接
- 右外连接
## 约束
- 主键约束
- 唯一约束
- 不可为空约束
- 外键约束
- check 约束
## 索引
- 主键索引
- 唯一索引
- 普通索引
- 全文索引
## 事务
- 事务说明	
- 事务的特性(acid)
- 事务的隔离级别
- 默认事务的隔离级别
## 存储引擎 engine
- myisam
- innerdb
- mermory
## 视图
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


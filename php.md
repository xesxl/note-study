# PHP笔记
## WAMP
	- apache
		apache -k install 安装服务
		apache -k uninstall 卸载服务
		apache -k start 启动服务
		apache -k stop 停止服务
	- 修改httpd.conf文件
		增加php处理模块
		LoadMoudle php5_module php中的php5apache2_4.dll路径
		<FilesMatch \.php$>
			SetHandler application/x-httpd-php
		</FilesMatch>
		PHPiniDir  -> php所在文件路径
	- 整合 mysql
		修改php.ini中的extenstion_dir 为正确目录
		将extension列表中的php_mysql.dll , php_mysqli.dll, php_pdo打开

## 基础
## 变量命名规范
	- php变量面前必须加上$
	- php变量名字区分大小写，函数名字不区分大小写
	- php变量名字可以是关键字，不推荐
	- 可以是驼峰法也可以是下划线法
## 语言特点
	动态弱数据脚本语言

### 数据类型
	- 整数
		#### 整数可以使用十进制，十六进制 或者八进制
		- 十进制 10
		- 十六进制 0x10
		- 八进制 010
		#### 整数的字节大小与平台有关通常是4个字节
		- 可以使用常量PHP_INT_SIZE查看int字节大小
		- 整数最大值可以使用 PHP_INT_MAX查看
		**整数超过最大值的范围会自动转成float类型**
	- 布尔值
		#### 布尔值的说明
			0, false, '', '0', null, 空数组, 空标记的smipleXml都为false, 其余为true
	- 浮点数
		#### 浮点数的精度
			浮点数的精度为14位，从左边第一个非0的数字开始计算
	- 字符串
		- 单引号
			单引号不会解析字符串中包含的变量
		- 双引号
			会解析字符串中包含的变量，如果变量数据类型复杂则使用{$var['name']}来使用
		- heredoc
			一般用于返回大段的html代码
			会解析包含的变量
			<<<HTMLCON
				任意内容
			HTMLCON;
		- nowdoc
			同上，但不解析包含的变量
			<<< 'HTMLCON'
			HTMLCON;
		- 特殊字符的转义 如果需要在字符串中使用转义字符则在字符前面加上\即可
	- 特殊类型 如 null
	- 数组
		- 索引数组
		- 关联数组
	- 对象
	- 资源类型
		- 文件资源
		- mysql资源
### 数据类型的转换
- 自动转换
	当不同数据类型的变量进行算术运算时，会向高精度的类型转换
- 强制转换
	- settype(变量名, '类型');
	- (类型)变量
	- floatval(变量) 或 intval(变量) 等



### 运算符
- 赋值运算符
	- =
- 数学运算符
	- \+
	- \-
	- \*
	- /
	- %
- 逻辑运算符
	- &&
	- ||
	- or
	- and
	- !
- 关系运算符
	- \<
	- \> 
	- \>=
	- \<=
	- ==
	- !=
	- ===
	- !==
- 位运算符
	- &
	- |
	- ^
	- ~
- 类型运算符
	- type()
	- (string) 变量名  强制类型转换
- 自增自减运算符
	- ++
	- --
- 执行运算符
 	- ``
- 错误控制运算符
	- @



### 流程控制
- 单分支
	- if else
	- switch case
- 多分支
	- for
	- while
	- do while
- 跳转到指定代码块
	- goto lab;

### 函数
- 函数定义
- 匿名函数
- 变量函数

###文件的引入
- require
- require_one
- include
- include_one

### 数组
- 数组的创建
- 数组的删除
- 数组的遍历
- 数组相关函数

###排序 和 查找算法
- 排序算法
	- 冒泡排序
	- 插入排序
	- 选择排序
	- 快速排序

- 查找算法
	- 遍历查找
	- 二分查找 

## 面向对象
### 三大特性
- 封装
- 继承
- 多态

### 访问控制符
- public
- protected
- private

### 魔术常量
- __file__
- __dir__
- __function__

### 魔术方法
- __call
- __clone
- __get
- __set
- __isset 
- __unset
- __toString

### 类
- 类常量 
- 类变量 -> 静态变量
- 类方法 -> 静态方法
- 关键字 static

### 抽象类
- 关键字 abstract 
- 抽象方法 
- 抽象类

### 接口
- interface 
- implement

### 其他数据转对象

### trait
- 关键字 trait
- use

### 序列化与反序列化
- 序列化
- 反序列化

### 类的自动加载
- __autoload

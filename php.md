# PHP笔记
## WAMP
- apache
	- apache -k install 安装服务
	- apache -k uninstall 卸载服务
	- apache -k start 启动服务
	- apache -k stop 停止服务
- 修改httpd.conf文件
	-增加php处理模块
	`LoadMoudle php5_module php中的php5apache2_4.dll路径
	<FilesMatch \.php$>
		SetHandler application/x-httpd-php
	</FilesMatch>
	PHPiniDir  -> php所在文件路径`
- 整合 mysql
	- 修改php.ini中的extenstion_dir 为正确目录
	- 将extension列表中的php_mysql.dll , php_mysqli.dll, php_pdo打开

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
	- settype(变量名, '类型') 将变量本身的类型改变;
	- (类型)变量 将变量的值转换后返回，支持数组
	- floatval(变量) 或 intval(变量) 等 将变量的值转换类型后返回，不支持数据
### 变量相关函数
	- isset(变量) 检测某个变量是否存在并且不为null
	- empty(变量) 检测某个变量是否为空, '', 0, '0', null, false 都为空
	- unset(变量) 将变量所在的空间回收并从符号表中删除该变量的名称
	- is_numeric(变量) 检测变量是否为整数
### 数据的传递方式
	- 普通传递, 将值拷贝一份后传递
		`
			$a = 1;
			$b = $a;
		`
	- 引用传递
		`
			$a = 1;
			$b = &$a;
		`
	> int, float, string, array 默认都是值传递
	**object 也是值传递，传递的是对象标识符中存放的指向对象数据空间的地址, 可以当成引用传递**
### 预定义全局变量
	- $GLOBALS
		预定义超全局数组，包含所有全局变量
	- $_POST
		所有POST请求的参数
	- $_GET
		所有GET请求的参数
	- $_SERVER
		当前服务器的信息
	- $FILE
		所有上传文件请求的参数
### 表达式
	任何有返回值的语句

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
- 三元运算符
	表达式 ? 表达式结果为真 : 表达式结果为假;
- 字符串连接符
	\.  `echo $str1 . $str2`
- 类型运算符 判断某个对象是否是某个类的实例
	对象 instanceof 类名
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
- 自增自减运算符
	- ++
	- --
- 执行运算符
 	- `` 将反引号中的内容当做外壳命令执行效果如同shell_exec();
- 错误控制运算符	
	- @ 放置在表达式之前，会忽略掉该表达式产生的错误信息
- 运算符的优先级
	- new clone 实例化， 克隆
	- array() 创建数组
	- ++ \-\- ~ @ (类型转换)
	- instanceof 类型运算符
	- \! 取反
	- * / %
	- + \- .字符串连接
	- \>\> \<\< 左移 右移
	- == === !== !=== 比较运算符
	


### 流程控制
- 单分支
	- if else
	- switch case
**模板替代语法**
	> 将所有的左大括号换成:,结尾对应相应的结束语句
		- if endif;
		- while endwhile;
		- for endfor;
	`
		<body>
			<?php if($age > 18):?>
				<h1>1232</h1>
			<?php endif; ?>
		</body>
	`
	
- 多分支
	- for
	- while
	- do while
- 跳转到指定代码块
	- goto lab;
- break
	可以结束当前的for, foreach, while, do-while, switch的执行
	break可以接受一个可选的参数表示终止的层数如: break 2; //跳出两层
- containue 跳转本次循环剩余代码执行下一次循环
	可以接受一个参数表示跳出的层数如: containue 2 表示跳出两层循环

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

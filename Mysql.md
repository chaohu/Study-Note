# Mysql学习笔记
[![Author](https://img.shields.io/badge/author-chaohu-lightgrey.svg)](https://github.com/chaohu)

### 一、基本信息
* 1.默认端口号：3306
* 2.超级用户：root
* 3.子查询（Subquery）：出现再其他SQL语句内的SELECT子句

### 二、语句规范
* 1.关键字与函数名称全部大写
* 2.数据库名称、表名称、字段名称全部小写
* 3.以分号结尾
* 4.{ }必选项、[ ]可选项

### 三、常用命令

#### 1.基础命令
* SELECT VERSION();	//显示当前服务器版本
* SELECT NOW();		//显示当前日期时间
* SELECT USER();		//显示当前用户
* SHOW WARNINGS;		//查看警告信息

#### 2.数据库
* CREATE {DATABASE | SCHEMA} [IF NOT EXISTS] db_name [DEFAULT] CHARACTER SET [=] charset_name			//创建数据库
* ALTER {DATABASE | SCHEMAS} [db_name] [DEFAULT] CHARACTER SET [=] charset_name						//修改数据库
* DROP {DATABASE | SCHEMAS} [IF EXISTS] db_name	//删除数据库
* SHOW {DATABASES | SCHEMAS};		//查看当前服务器下的数据库列表

#### 3.数据表
* CREATE TABLE [IF NOT EXISTS] table_name(column_name data_type,...)	//创建数据表
* SHOW TABLES [FROM db_name] [LIKE 'pattern' | WHERE expr]	//查看数据表
* SHOW COLUMNS FROM tb1_name		//查看数据表结构
* SHOW INDEXES FROM tb1_name		//查看索引
* ALTER TABLE tb1_name ADD [COLUMN] co1_name column_definition [FIRST | AFTER co1_name]						//添加单列
* ALTER TABLE tb1_name ADD [COLUMN] \(co1_name column_definition,...\)	//添加多列
* ALTER TABLE tb1_name DROP [COLUMN] co1_name	//删除列

#### 4.记录
* INSERT [INTO] tb1_name[(col_name,...)] {VALUES | VALUE}({expr | DEFAULT},...),(...),...							//插入记录
* INSERT [INTO] tb1_name SET co1_name={expr | DEFAULT},...	//插入记录（可以使用子查询SubQuery）
* INSERT [INTO] tb1_name [(co1_name,...)] SELECT ...		将查询结果插入到指定数据表
* UPDATE [LOW_PRIORITY] [IGNORE] table_reference SET co1_name1={expr1|DEFAULT} [,co1_name2={expr2|DEFAULT}]...
* DELETE FROM tb1_name [WHERE where_condition]	//删除记录（单表删除）
* SELECT select_expr [,select_expr...] [FROM table_references [SHERE shere_condition] [GROUP BY {co1_name | position} [ASC|DESC],...] [HAVING where_condition] [ORDER BY {co1_name | expr | positoin} [ASC | DESC],...] [LIMIT {[offset,] row_count|row_count OFFSET offset}]	//记录查找
* [GROUP BY {co1_name | position} [ASC | DESC],...	//查询结果分组
* [HAVING where_condition]	//分组条件
* [ORDER BY {co1_name | expr | posotion} [ASC | DESC],...}	//对查询结果进行排序
* [LIMIT {[offset,] row_count | row_count OFFSET offset}]		//限制查询结果返回的数量

### 四、数据类型

#### 1.整形
* TINYINT	(1字节)
* SMALLINT	(2字节)
* MEDIUMINT	(3字节)
* INT		(4字节)
* BEGINT	(8字节)

#### 2.浮点型	(M 数字总位数，D 小数点后面的位数)
* FLOAT[(M,D)]
* DOUBLE[(M,D)]

#### 3.日期时间类型
* YEAR
* TIME
* DATA
* DATETIME
* TIMESTAMP

#### 4.字符型
* CHAR(M)
* VARCHAR(M)
* TINYTEXT
* TEXT
* MEDIUMTEXT
* LONGTEXT
* ENUM('value1','value2',...)
* SET('value1','value2',...)

### 五、数据属性

NULL/NOT NULL	//数据可以为空/不能为空

AUTO_INCREMENT	//自动编号，且必须与主键组合使用

PRIMARY KEY		//主键约束，自动为NOT NULL，每张表只有一个

UNIQUE KEY		//唯一约束，可以为空、多个

FOREIGN KEY		//外键约束

* CASCADE:从父表删除或更新且自动删除或更新子表中匹配的行
* SET NULL:从父表删除或更新行，并设置子表中的外键列为NULL。如果使用该选项，必须保证子表列没有指定的外键列
* RESTRICT:拒绝对父表的删除或更新操作
* NO ACTION:标准SQL关键字，在MySQL中与RESTRICT相同

DEFAULT			//默认值

### 六、内置函数

#### 1.字符函数

* CONCAT()		//字符连接
* CONCAT_WS()	//使用指定的分隔符进行字符连接
* FORMAT()		//数字格式化
* LOWER()		//转换成小写字母
* UPPER()		//转换成大写字母
* LEFT()		//获取左侧字符
* RIGHT()		//获取右侧字符
* LENGTH()		//获取字符串长度
* LTRIM()		//删除前导空格
* RTRIM()		//删除后续空格
* TRIM()		//删除前导和后续空格
* SUBSTRING()	//字符串截取
* [NOT] LIKE	//模式匹配
* REPLACE()		//字符串替换

#### 2.数字运算符与函数
* CEIL()		//进一取整
* DIV			//整数除法
* FLOOR()		//舍一取整
* MOD			//取余数（取模）
* POWER()		//幂运算
* ROUND()		//四舍五入
* TRUNCATE()	//数字截取

#### 3.比较运算符与函数
* [NOT] BETWEEN...AND...	//[不]在范围之内
* [NOT] IN()				//[不]在列出值范围内
* IS [NOT] NULL				//[不]为空

#### 4.日期时间函数
* NOW()			//当前日期和时间
* CURDATE()		//当前日期
* CURTIME()		//当前时间
* DATE_ADD()	//日期变化
* DATEDIFF()	//日期差值
* DATE_FORMAT()	//日期格式化

#### 5.信息函数
* CONNECTION_ID()	//连接ID
* DATEBASE()		//当前数据库
* LAST_INSERT_ID()	//最后插入记录
* USER()			//当前用户
* VERSION()			//版本信息

#### 6.聚合函数
* AVG()			//平均值
* COUNT()		//计数
* MAX()			//最大值
* MIN()			//最小值
* SUM()			//求和

#### 7.加密函数
* MD5()			//信息摘要算法
* PASSWORD()	//密码算法

### 七、自定义函数

* 创建自定义函数

CREATE FUNCTION function_name RETURNS {STRING|INTEGER|REAL|DECIMAL} routine_body

* 删除函数

DROP FUNCTION [IF EXISTS] function_name

### 八、存储过程

* 创建存储过程

CREATE

[DEFINER = {user | CURRENT_USER}]

PROCEDURE sp_name ([proc_parameter[,...]])

[characteristic ...] routine_body

proc_parameter:

[IN | OUT | INOUT] param_name type

* 修改存储过程

ALTER PROCEDURE ap_name [characteristic ...]

COMMENT 'string'

|{CONTAINS SQL | NO SQL | READS SQL DATA | MODIFIES SQL DATA}

| SQL SECURITY {DEFINER | INVOKER}

* 删除存储过程

DROP PROCEDURE [IF EXISTS] sp_name

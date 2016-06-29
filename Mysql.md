# Mysql学习笔记
[![Author](https://img.shields.io/badge/author-chaohu-lightgrey.svg)](https://github.com/chaohu)

### 一、基本信息
* 1.默认端口号：3306
* 2.超级用户：root

### 二、语句规范
* 1.关键字与函数名称全部大写
* 2.数据库名称、表名称、字段名称全部小写
* 3.以分号结尾
* 4.{ }必选项、[ ]可选项

### 三、常用命令

SELECT VERSION();	//显示当前服务器版本

SELECT NOW();		//显示当前日期时间

SELECT user();		//显示当前用户

CREATE {DATABASE | SCHEMA} [IF NOT EXISTS] db_name [DEFAULT] CHARACTER SET [=] charset_name			//创建数据库

ALTER {DATABASE | SCHEMAS} [db_name] [DEFAULT] CHARACTER SET [=] charset_name						//修改数据库

DROP {DATABASE | SCHEMAS} [IF EXISTS] db_name	//删除数据库

SHOW {DATABASES | SCHEMAS};	//查看当前服务器下的数据表列表

SHOW WARNINGS;		//查看警告信息

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

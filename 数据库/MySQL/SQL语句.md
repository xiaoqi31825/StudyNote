## SQL语句

### 0、概述
- SQL语句分类：数据查询、数据定义、数据操纵、数据控制、事务控制、系统管理、数据库管理、视图管理、函数管理、存储过程管理、触发器管理、事件管理、权限管理、其他语句
- 书写规则: 
  - 各个数据库的语法不完全相同,因此尽量书写标准SQL语句。
  - SQL语句不区分大小写,但标准SQL语句建议: a.SQL关键字大写 b.所有列名和表名小写 c.常量使用''引起来
  - 每列设置not null约束(原因:考虑null时的条件判断会异常复杂,会涉及到三值逻辑,因此尽量不要出现null的行)
  - 语句以;结尾


### 1、数据查询(DQ)语句
#### 概念
- 最基本的SQL语句: 只对数据进行查询,不会对数据进行修改。
- 用于: 从数据库中查询(SELECT)数据,并返回结果。

#### 语句
...


### 2、数据定义(DD)语句
#### 概念
- 最复杂的SQL语句: 涉及数据库对象(模式、表、视图、索引、触发器、存储过程、函数)的操作。
- 用于: 对数据库、数据库对象进行创建(CREATE)、修改(ALTER)、删除(DROP)等。

#### 语句
##### 数据库(DATABASE) | 模式(SCHEMA)
- 查看数据库版本:
  ```mysql
  SELECT VERSION();
  ```
- 查看数据库字符集: 
  ```mysql
  SHOW VARIABLES LIKE 'char%';
  ```
- 查看数据库排序规则:
  ```mysql 
  SHOW VARIABLES LIKE 'collate%';
  ```
- 查看数据库创建时间: 
  ```mysql
  SHOW CREATE DATABASE `db_name`;
  `````
- 查看当前的系统时间: 
  ```mysql
  SELECT NOW();
  ```
- 查看数据库列表: 
  ```mysql
  SHOW DATABASES;
  ```
- 选择数据库: USE
  ```mysql
  USE `db_name`;
  ```
- 查看当前使用的数据库: 
  ```mysql
  SELECT DATABASE();
  ```
- 创建数据库: CREATE DATABASE
  ######  需求: 如果不存在名为db_course_demo的数据库, 则创建db_course_demo数据库, 默认字符集为utf8, 排序规则为utf8_general_ci。
  ```mysql
  CREATE DATABASE IF NOT EXISTS `db_course_demo`
  DEFAULT CHARSET utf8 
  DEFAULT COLLATE utf8_general_ci; 
  ```
-  修改数据库: ALTER DATABASE
  ###### 需求: 修改db_course_demo数据库的默认字符集为utf8mb4。
  ```mysql
  ALTER DATABASE `db_course_demo`
  DEFAULT CHARSET utf8mb4;
  ```
- 删除数据库: DROP DATABASE
  ###### 注意: 1) 数据库删除后, 该数据库下的所有数据也会被删除, 故谨慎操作。
  ###### 2) 如果不加IF EXISTS：当实际数据库不存在名为db_course_demo的数据库, 会返回报错。
  ###### 3) 应该加上IF EXISTS: 当实际数据库存在名为db_course_demo的数据库则删除此数据库, 如果不存在此数据库不会报错。
  ```mysql
  DROP DATABASE IF EXISTS `db_course_demo`;
  ```
  
##### 表
- 查看表结构: DESC | {desc product};
- 查看表创建语句: SHOW CREATE TABLE
- 查看表索引: SHOW INDEX FROM

- 创建表: CREATE TABLE
  ```mysql
  
  ```
  ###### 结构说明:


- 修改表: ALTER TABLE
- 删除表: DROP TABLE
- 复制表: CREATE TABLE ... AS SELECT...
- 导入数据: LOAD DATA INFILE
- 导出数据: SELECT ... INTO OUTFILE
- 优化表: OPTIMIZE TABLE
- 锁定表: LOCK TABLES
- 解锁表: UNLOCK TABLES
- 重命名表: RENAME TABLE
- 复制表结构: CREATE TABLE ... LIKE ...
- 复制表数据: INSERT INTO ... SELECT ... FROM ...
- 统计表数据量: SELECT COUNT(*) FROM ...
- 统计表行数: SELECT TABLE_ROWS FROM information_schema.TABLES WHERE TABLE_SCHEMA = 'db_name' AND TABLE_NAME = 'table_name';
- 统计表大小: SELECT DATA_LENGTH + INDEX_LENGTH FROM information_schema.TABLES WHERE TABLE_SCHEMA = 'db_name' AND TABLE_NAME = 'table_name';

##### 视图
##### 索引
##### 触发器
##### 存储过程
##### 函数
 

### 3、数据操纵(DM)语句
#### 概念
- 用于: 对数据库对象进行检索(SELECT)、插入(INSERT)、更新(UPDATE)、删除(DELETE)等。

#### 语句
...


### 4、数据控制(DC)语句
#### 概念
- 以控制用户的访问权限为主。
- 用于: 安全管理(包括用户管理、权限管理、安全审计、密码管理等)

#### 语句
...


### 5、事务控制(TC)语句
#### 概念
- 用于: 事务处理(包括事务开始、提交、回滚等)
- 事务: 一个或一组SQL语句组成的工作单元, 要么全部执行成功, 要么全部失败。
- 事务的特性: 原子性、一致性、隔离性、持久性。
- 事务控制语句: 事务开始(START TRANSACTION)、事务提交(COMMIT)、事务回滚(ROLLBACK)。

#### 语句
...


### 6、系统管理(SM)语句
### 7、数据库管理(DB)语句
### 8、视图管理(VW)语句
### 9、函数管理(FN)语句
### 10、存储过程管理(SP)语句
### 11、触发器管理(TR)语句
### 12、事件管理(EV)语句
### 13、权限管理(PM)语句
### 14、其他语句

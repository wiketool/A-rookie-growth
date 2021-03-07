# 2021-03-06

## Mysql

### 三大范式

1. 第一范式(确保每列保持原子性)
2. 第二范式(确保表中的每列都和主键相关)
3. 第三范式(确保每列都和主键列直接相关,而不是间接相关)

### 基本语法

#### DDL - 数据定义语言（数据库、表、列）

##### CRUD - 操作数据库

1. Create - 创建
   - `create database if not exists xxx` 创建数据库(如果没有存在)
   - `··· character set xxx` 指定字符集 xxx
2. Retrieve - 查询
   - `show create database mysql` 查看某个数据库的创建语句
   - `show databases`  查询数据库的名称
3. Update - 修改
   1. `alter database xxx character set yyy` 修改数据库的字符集
4. Delete - 删除
   1. `drop database if exist xxx` 删除数据库
5. 使用数据库
   1. `use xxx`
   2. `select database()` 选中当前的数据库

##### 对表操作

1. Create

   - create table 表名(
     				列名1 数据类型1,
           				列名2 数据类型2,
           				....
           				列名n 数据类型n
     );

   - 复制表

     `create table xxx like xxx` 

2. Retrieve

   - `show tables`
   - 查询表结构 `desc xxx`

3. Update

   - 修改表名
     alter table 表名 rename to 新的表名;
   - 修改表的字符集
     alter table 表名 character set 字符集名称;
   - 添加一列
     alter table 表名 add 列名 数据类型;
   - 修改列名称 类型
     alter table 表名 change 列名 新列别 新数据类型;
     alter table 表名 modify 列名 新数据类型;
   - 删除列
     alter table 表名 drop 列名;

4. Delete

   - drop tabel if exists xxx;

#### DML - 数据操作语言（增删查改表中的数据）

1. 增加数据

   - `insert into xxx (column name , ···) values (value 1,···)`

     除了数字以外，其他类型需要使用引号引起来

2. 删除数据

   - `delete from xxx where yyy`

     若不加条件，则删除整张表

     删除整张表高效的方法

     `truncate table xxx;`

3. 修改数据

   - `update xxx set [column] = [value] WHERE CONDICTION`

#### DQL - 数据查询语言

1. `SELECT * FROM [TABLE NAME]`

   **where** 条件列表

   **group by** 分组字段

   **having** 分组之后的条件

   **order** 排序

   **limit** 分页限定

2. 去除重复

   `select distinct 字段 from [table name];`

3. 多字段查询

   ``select id,name,math +ifnull(english,0) as `总分` from test ``
   
4. 条件查询

   < , > , <= , >= , = , != , <> 不等于

   AND  &&

   OR ||

   BETWEEN ... AND ... (>= && <=) 

   IN (22,15,18)    在集合中的数

   IS NULL

   IS NOT NULL

5. 模糊查询

   LIKE ...

   ​		_  :单个任意字符

   ​		% :多个任意字符

6. 排序查询

   ORDER BY 排序字段1  排序方式 , ...

   ​		排序方式

   ​				ASC  升序排序

   ​				DESC  降序排序

7. 聚合函数

   ​	COUNT()

   ​	MAX()

   ​	MIN()

   ​	SUM()

   ​	AVG()

8. 分组查询

   SELECT AVG(math) , MAX(math) FROM test WHERE ... GROUP BY SEX HAVING ...

   ​		`WHERE ...` 在分组前进行条件限定

   ​		`HAVING ...` 在分组后进行条件限定

9. 分页查询

   LIMIT 开始的索引,索引的条数

#### DCL - 数据控制语言

1. ##### 约束

   1. 非空约束

      ```sql
      create table test(
      	id int NOt NULL
      )
      alter table test modify id int NOt NULL
      alter table test modify id int 
      ```

   2. 唯一约束  UNIQUE

      · 唯一约束下的列的值可以有多个NULL

   3. 主键约束 PRIMARY KEY

      - 删除主键

        `ALTER TABLE test DROP PRIMARY KEY`

      - 一张表只能有一个主键
      - 主键字段NOT NULL && UNIQUE
      - 主键后可以跟随 `AUTO_INCREMENT`（自动增长）

   4. 外键约束

      ```sql
      create table xxx(
      	...
          外键列
          constraint 外键名称 foreign key (外键列名称) 		references 主表名(列字段名)
      )
      
      alter table test drop primary key 外键名称
      
      alter table test add constraint ...
      ```

      - 级联更新

        在外键设置的最后面加上 ON UPDATE CASCADE 

      - 级联删除

        ON DELETE CASCADE


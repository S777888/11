### 创建数据库

```
CREATE DATABASE 库名;  -- ";"sql语句以分号结尾,create等关键字也可以小写，只是规范习惯用大写表示关键字(我更喜欢小写)
```
例如想创建一个名为 "S777888" 的数据库
```
CREATE database s777888; -- sql不区分大小写
```
然后使用这个库 "**use**"
```
use s777888    -- use可以不用分号
```
以及各种"Show"查看指令
```
show databases; //查看全部数据库
show tables; //查看全部数据表
```
接下来就是对数据库的"增删改查".

#### 1.创建数据表
```
create table test1
(                                      -- SQL语句中前后的空格都被忽略，SQL语句可以写成长长的一行，也可以分写在多行。
id int auto_increment primary key,     -- primary key 含义是主键，每个数据表必须含有主键，否则会报错
lastname varchar(20) not null,         -- varchar( M )代表长度在 M 字节以内,M取值范围在0~65535之间
firstname char(20),                    -- char( M ),M的取值范围在0~255之间
city varchar(10)
);                                     -- 多数SQL开发人员认为，将SQL语句分成多行更容易阅读和调试。
```
varchar( M )和char( M )的区别不仅仅在于长度限定范围，例如char(10)，不论你存储的数据是否有10个字节，都会占去10字节的空间，不足10字节的位置用空格填充。
CHAR存储**固定**长度数据很方便，CHAR字段上的索引效率极高。

varchar保存数据时只保存(需要的长度)+1,'+1'这一字节是记录长度,varchar存储**可变**长度数据,但存储效率没有CHAR高。
从空间上考虑,用varchar合适。

**not null** 表示不允许'**null**'值。
**auto_increment** 表示自动递增，每多一条数据就递增+1。

#### 2.插入数据 ####
```
insert into test1
(id,lastname,firstname,firstname.city) values(1,'a1','a2','武汉');
Query OK,1 row affected 就表示添加成功了
```







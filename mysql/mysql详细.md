# DML

DML是数据操作语言,主要是对数据表的操作

### （1）插入数据(insert into)

数据表插入数据分为全字段插入数据和部分字段插入数据

①全字段插入数据（有两种方法，推荐第一种方法）

```sql
--有多少个字段,就要写多少个值,且是一一对应的
insert into 表名 values(值1,值2,值3...值n);

--此方法要写出所有字段,并一一对应插入值
insert into 表名(字段1,字段2...字段n) values(值1,值2...值n);
```

②部分字段插入数据

```sql
--部分字段插入数据，只写需要插入数据的字段名
insert into 表名(字段1,字段2...) values(值1,值2...);
```

### （2）删除数据(delete / truncate)

```sql
--删除表中所有数据
delete from 表名;

--删除表中指定的数据
delete from 表名 where 字段 = 值;
```

### （3）修改数据(update)

```sql
--有限制条件的修改,只修改特定记录
update 表名 set 字段 = 值 where 条件(字段 = 值);
```

#  DQL

DQL是数据查询语言，主要就是select配合其他限制条件的关键字进行查询

### （1）无条件查询

```sql
--查询表中所有数据
select *from 表名;
```

### （2）查询在...到...之间(between and / && / and)

```sql
--查询users表中年龄在18~25岁之间的记录
--方式1 between..and..
select *from users where age between 18 and 25;

--方式2 &&
select *from users where age>=18 && age<=25;

--方式3 and
select *from users where age>=18 and age<=25;
```

### （3）指定条件查询

**①单个条件(or / in)**

```sql
--查询users表中年龄为18,20,25岁的记录
--方式1 or
select *from users where age=18 or age=20 or age=25;

--方式2 in
select *from users where age in(18,20,25);
```

**②多个条件(and)**

```sql
--查询users表中年龄为23，性别为女，名字为小楠的记录
select *from users where age=23 and gender='女' and name='小楠'; 
```

### (4)查询不为NULL值(is not null),为NULL值(is null)

```sql
--查询users表中序号不为空的记录
select *from users where id is not null;

--查询user表中序号为空的记录
select *from users where id is null;
```

### (5)模糊查询（like）

```sql
_:单个任意字符

%:多个任意个字符

--查询users表中姓名第一个字为李的记录
select *from users where name like '李%';

--查询users表中姓名第二个字为李的记录
select *from users where name like '_李%';

--查询users表中姓名含有李字的记录
select *from users where name like '%李%';

--查询users表中姓名是两个字的记录
select *from users where name like '__';
```

### (6)去除重复记录查询（distinct）

```sql
--查询users表中所在城市不相同的记录
--select distinct 字段 from 表名;
select distinct city from users;
```

### (7)排序查询（order by）

**①单个条件**

```sql
--查询users表中记录，并以年龄升序排序
select *from users order by age; --默认升序

--查询users表中记录，并以年龄降序排序
select *from users order by age desc;--desc降序
```

**②多个条件**

注意：多个排序条件时，只有当第一个排序条件值一样，才会执行第二个排序条件，以此类推

```sql
--查询users表中记录，并体育成绩降序，年龄降序

select *from users order by PE desc,age desc;
```

### （8）聚合函数

**①计算和（sum）**

```sql
select sum(字段) (as sumvalue) from 表名;
```

**②计算最大值（max）**

```sql
select max(字段) (as maxvalue) from 表名;
```

**③计算最小值（min）**

```sql
select min(字段) (as minvalue) from 表名;
```

**④计算平均值（avg）**

```sql
select avg(字段) (as avgvalue) from 表名;
```

**⑤计算个数（count）**

```sql
select count(字段) (as totalcount) from 表名;
```

### (9)分组查询（group by）

```sql
--查询users表中的记录，按照性别分组，查询男，女的体育成绩平均分
select gender,avg(PE) from users group by gender;

--查询users表中的记录，按照性别分组,分别查询男、女的体育成绩平均分,人数
select gender, avg(PE),count(id) from users group by gender;

--查询users表中的记录, 按照性别分组,分别查询男、女的体育成绩平均分,人数 要求:分数低于60分的人，不参与分组
select gender, avg(PE),count(id) from users where PE > 60 group by gender; 

 --查询users表中的记录,按照性别分组,分别查询男、女的体育成绩平均分,人数 要求:分数低于60分的人，不参与分组,分组之后,人数要大于2个人
select gender,avg(PE),count(id) from users where PE > 60 group by gender having count(id)>2;
```

### (10)分页查询（limit）

注意：第一条记录的索引是0

```sql
--查询users表中的前10行条记录
select *from users limit 10;

--查询users表中第2~11条记录 (从第2条记录开始累加10条记录)
select *from users limit 1,10;

--查询users表中第5~17条记录 (从第5条记录开始累加13条记录)
select *from users limit 4,13;
```

### （11）内连接查询

如果查询数据的来源来自多张表，则必须对这些表进行连接查询，连接是把不同表的记录连到一起的最普遍的方法，通过连接查询可将多个表作为一个表进行处理，连接查询分为内连接和外连接

语法格式

```sql
--语法1 （隐式内连接）
select 字段1,字段2...
from 表1,表2...
where 过滤条件;

--语法2 （显式内连接）
select 字段1,字段2...
from 表1 inner join 表2 ...
on 过滤条件;
```



### （12）外连接查询

外连接查询分为左外连接查询和右外连接查询

语法

```sql
--左外连接
select 字段1,字段2..
from 表1 left (outer) join 表2 on 过滤条件;

--右外连接
select 字段1,字段2..
from 表1 right (outer) join 表2 on 过滤条件;
```
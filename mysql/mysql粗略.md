#### 查询

```
查询全表
select *from student [where id="10" ]  查询id为10的所有学生信息
分组查询
select count(id) from student where grade>60 group by sex  查询按照性别分组的学生男女分别的数量
分组查询符合的组筛选
select cout(id) from student where grade>60 group by sex having cout(id)>2 查询按照性别分组的学生男女分别的数量 只显示人数大于2的
去重
select distinct class from student where grade>60 查询所在班级不同成绩大于60分的学生
查询没规律的多条数据 in
select  * from student where in(grade=60,grade=80) 查询分数为60和80分成绩的学生
```

#### 插入

```
插入一条数据
insert into from student  ("10","男") values ("id","男")
insert into 表名(字段1,字段2...) values(值1,值2...);
```

#### 更新

```
更新 id = 10 的数据性别为男
update from student set sex="男" where id = "10"
update 表名 set 字段 = 值 where 条件(字段 = 值);
```

#### 删除

```
删除id =10的学生
delete from student where id="10"
--删除表中指定的数据
delete from 表名 where 字段 = 值;
```


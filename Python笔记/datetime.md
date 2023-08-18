1.date ：datetime.date(year,month,day)

```python
import datetime
t=datetime.date(2019,8,26)
print(type(t))
print(t.day,t.month,t.year)
#<class 'datetime.date'>
#26 8 2019
```

2.获取当天日期
语法：datetime.date.today

```python
import datetime
a = datetime.date.today()
print(a)
print(a.year,a.month,a.day)
#2019-08-26
#26 8 26
```

3.**weekday方法**

语法：date对象.weekday()
返回weekday，如果是星期一，返回0，如果星期2，返回1

4.**replace替换方法**

语法：date对象.replace(year,month,day)
返回一个替换指定日期字段的新date对象。注意替换是产生新对象，不影响原date对象

5.**max属性**

语法:datetime.date.max
返回date类所能表示的最大年、月、日数值

6.**min属性**

语法：datetime.date.min
返回date类所能表示的最小年、月、日数值

7.**now()**

语法：datetime.datetime.now()
返回值：返回当前本地日期时间

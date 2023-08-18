## 1. time.localtime()

将一个时间戳转换为当前时区的 struct_time。若未提供参数，则以当前时间为准。

```python
print(time.localtime())

>> time.struct_time(tm_year=2021, tm_mon=9, tm_mday=16, tm_hour=8, tm_min=47, tm_sec=50, tm_wday=3, tm_yday=259, tm_isdst=0)

print(time.localtime(time.time())) # 可以传入一个时间戳参数

>> time.struct_time(tm_year=2021, tm_mon=9, tm_mday=16, tm_hour=8, tm_min=47, tm_sec=50, tm_wday=3, tm_yday=259, tm_isdst=0)

```



## 2. time.time()

返回当前时间的时间戳。

```python
print(time.time())

>> 1631753270.998875
```



## 3. time.mktime(t)

将一个 struct_time 转化为时间戳

```python
print(time.mktime(time.localtime()))

>> 1631757172.0
```



## 4. time.asctime()

把一个表示时间的元组或者 struct_time 表示为这种形式：‘Sun Jun 20 23:21:05 1993’。如果没有参数，将会将`time.localtime()`作为参数传入。

```python
print(time.asctime())

>> Thu Sep 16 09:52:52 2021
```



## 5. time.ctime()

把一个时间戳（按秒计算的浮点数）转化为`time.asctime()`的形式。如果参数未给或者为 None 的时候，将会默认`time.time()`为参数

```python
print(time.ctime())
print(time.ctime(time.time()))

>> Thu Sep 16 09:59:41 2021
>> Thu Sep 16 09:59:41 2021
```



## 6. time.strftime(format,[t])

把一个代表时间的元组或者 struct_time（如由`time.localtime()`返回）转化为格式化的时间[字符串](https://so.csdn.net/so/search?q=字符串&spm=1001.2101.3001.7020)。如果参数`t`未指定，将传入`time.localtime()`。

```python
print(time.strftime("%Y-%m-%d %H:%M:%S", time.localtime()))
print(time.strftime("%Y年-%m月-%d日 %H:%M:%S", time.localtime()))

>> 2021-09-16 09:59:41
>> 2021年-09月-16日 10:03:35
```

## 7.time.sleep(t)

```python
time.sleep(t)
#推迟执行的秒数
```



```python
元组(struct_time)：struct_time 元组共有 9 个元素，返回 struct_time 的函数主要有gmtime()，localtime()，strptime()。元组中的 9 个元素如下：

tm_year：年
tm_mon：月
tm_mday：日
tm_hour：时
tm_min：分
tm_sec：秒
tm_wday：一周的第几日
tm_yday：一年的第几日
tm_isdst：夏令时
```


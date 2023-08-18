```
series:
s=pd.Series( data, index, dtype, copy)
eg s = pd.Series(data,index=[100,101,102,103])
data	输入的数据，可以是列表、常量、ndarray 数组等。
index	索引值必须是惟一的，如果没有传递索引，则默认为 np.arrange(n)。
dtype	dtype表示数据类型，如果没有提供，则会自动判断得出。
copy	表示对 data 进行拷贝，默认为 False。
属性
axes	以列表的形式返回所有行索引标签。
dtype	返回对象的数据类型。
empty	返回一个空的 Series 对象。
ndim	返回输入数据的维数。
size	返回输入数据的元素数量。
values	以 ndarray 的形式返回 Series 对象。
index	返回一个RangeIndex对象，用来描述索引的取值范围
方法
head() 返回前n行数据，默认显示前5行数据
tail() 返回的是后n行数据，默认为后5行
isnull() 和 nonull() 用于检测 Series 中的缺失值。所谓缺失值，顾名思义就是值不存在、丢失、缺少。
isnull()：如果为值不存在或者缺失，则返回 True。
notnull()：如果值不存在或者缺失，则返回 False。
```


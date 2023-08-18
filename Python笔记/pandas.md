

```
dataframe:
pd.DataFrame( data, index, columns, dtype, copy)
参数:
data	输入的数据，可以是 ndarray，series，list，dict，标量以及一个 DataFrame。
index	行标签，如果没有传递 index 值，则默认行标签是 np.arange(n)，n 代表 data 的元素个数。
columns	列标签，如果没有传递 columns 值，则默认列标签是 np.arange(n)。
dtype	dtype表示每一列的数据类型。
copy	默认为 False，表示复制数据 data。
嵌套创建
data = [['Alex',10],['Bob',12],['Clarke',13]]
df = pd.DataFrame(data,columns=['Name','Age']) #
字典嵌套创建
data = {'Name':['Tom', 'Jack', 'Steve', 'Ricky'],'Age':[28,34,29,42]} 
df = pd.DataFrame(data)# 
列表嵌套创建
data = [{'a': 1, 'b': 2},{'a': 5, 'b': 10, 'c': 20}] 
df = pd.DataFrame(data)#
series嵌套创建:
d = {'one' : pd.Series([1, 2, 3], index=['a', 'b', 'c']),
   'two' : pd.Series([1, 2, 3, 4], index=['a', 'b', 'c', 'd'])}

```

```
列:
列索引添加:
d = {'one' : pd.Series([1, 2, 3], index=['a', 'b', 'c']),
   'two' : pd.Series([1, 2, 3, 4], index=['a', 'b', 'c', 'd'])}
df = pd.DataFrame(d)
#使用df['列']=值，插入新的数据列
df['three']=pd.Series([10,20,30],index=['a','b','c'])
print(df)
#将已经存在的数据列做相加运算
df['four']=df['one']+df['three']
insert() 插入:
info=[['Jack',18],['Helen',19],['John',17]]
df=pd.DataFrame(info,columns=['name','age'])
print(df)
#注意是column参数
#数值1代表插入到columns列表的索引位置
df.insert(1,column='score',value=[91,90,75])
通过 del 和 pop() 都能够删除 DataFrame 中的数据列：
del data['one']
pd.pop(data['one'])
```

```
行:
可以将行标签传递给 loc 函数 loc 允许接两个参数分别是行和列，参数之间需要使用“逗号”隔开，但该函数只能接收标签索引。
d = {'one' : pd.Series([1, 2, 3], index=['a', 'b', 'c']),
   'two' : pd.Series([1, 2, 3, 4], index=['a', 'b', 'c', 'd'])}
df = pd.DataFrame(d)
print(df.loc['b']) #
iloc 允许接受两个参数分别是行和列，参数之间使用“逗号”隔开，但该函数只能接收整数索引。
d = {'one' : pd.Series([1, 2, 3], index=['a', 'b', 'c']),
   'two' : pd.Series([1, 2, 3, 4], index=['a', 'b', 'c', 'd'])}
df = pd.DataFrame(d)
print (df.iloc[2]）#
切片操作多行选取
d = {'one' : pd.Series([1, 2, 3], index=['a', 'b', 'c']),
   'two' : pd.Series([1, 2, 3, 4], index=['a', 'b', 'c', 'd'])}
df = pd.DataFrame(d)
#左闭右开
print(df[2:4])#
使用 append() 函数，可以将新的数据行添加到 DataFrame 中，该函数会在行末追加数据行
df = pd.DataFrame([[1, 2], [3, 4]], columns = ['a','b'])
df2 = pd.DataFrame([[5, 6], [7, 8]], columns = ['a','b'])
#在行末追加新数据行
df = df.append(df2)
print(df)#
drop可以使用行索引标签，从 DataFrame 中删除某一行数据。如果索引标签存在重复，那么它们将被一起删除。
df = pd.DataFrame([[1, 2], [3, 4]], columns = ['a','b'])
df2 = pd.DataFrame([[5, 6], [7, 8]], columns = ['a','b'])
df = df.append(df2)
print(df)
#注意此处调用了drop()方法
df = df.drop(0)
print (df)
```

```
属性:
T	行和列转置。
axes	返回一个仅以行轴标签和列轴标签为成员的列表。
dtypes	返回每列数据的数据类型。
empty	DataFrame中没有数据或者任意坐标轴的长度为0，则返回True。
ndim	轴的数量，也指数组的维数。
shape	返回一个元组，表示了 DataFrame 维度。
size	DataFrame中的元素数量。
values	使用 numpy 数组表示 DataFrame 中的元素值。
head()	返回前 n 行数据。
tail()	返回后 n 行数据。
shift()	将行或列移动指定的步幅长度
方法:head() tail() 同样使用
shift()移动行或列：
peroids	类型为int，表示移动的幅度，可以是正数，也可以是负数，默认值为1。
freq	日期偏移量，默认值为None，适用于时间序。取值为符合时间规则的字符串。
axis	如果是 0 或者 "index" 表示上下移动，如果是 1 或者"columns" 则会左右移动。
fill_value	该参数用来填充缺失值。

info.shift(periods=3)  
结果：   
	a_data  b_data  c_data
0     NaN     NaN     NaN
1     NaN     NaN     NaN
2     NaN     NaN     NaN
3    40.0    20.0    22.0
4    28.0    37.0    17.0
```

```
描述性统计
count()	统计某个非空值的数量。
sum()	求和
mean()	求均值
median()	求中位数
mode()	求众数
std()	求标准差
min()	求最小值
max()	求最大值
abs()	求绝对值
prod()	求所有数值的乘积。
cumsum()	计算累计和，axis=0，按照行累加；axis=1，按照列累加。
cumprod()	计算累计积，axis=0，按照行累积；axis=1，按照列累积。
corr()	计算数列或变量之间的相关系数，取值-1到1，值越大表示关联性越强。
```

```
读文件:
CSV文件读取
df=pandas.read_csv('C:/Users/Administrator/Desktop/hrd.csv') 
json读取文件 
data=pd.read_json('C:/Users/Administrator/Desktop/hrd.json') 
SQL数据库读取
pip install pysqlite3
import sqlite3 
con = sqlite3.connect("database.db")  
#con参数指定操作数据库的引擎，可以指定，也可默认
df = pd.read_sql_query("SELECT * FROM information",con)
```

```
读写文件:
read_csv() 表示从 CSV 文件中读取数据，并创建 DataFrame 对象。
#需要注意文件的路径
df=pd.read_csv("C:/Users/Administrator/Desktop/person.csv")
print (df)
查看每一列的dtype:
#转换salary为float类型
df=pd.read_csv("C:/Users/Administrator/Desktop/person.csv",dtype={'Salary':np.float64})
print(df.dtypes)
更改文件标头名:
df=pd.read_csv("C:/Users/Administrator/Desktop/person.csv",names=['a','b','c','d','e'])
print(df)
skiprows参数表示跳过指定的行数。
df=pd.read_csv("C:/Users/Administrator/Desktop/person.csv",skiprows=2)
print(df)
Pandas 提供的 to_csv() 函数用于将 DataFrame 转换为 CSV 数据。如果想要把 CSV 数据写入文件，只需向函数传递一个文件对象即可。否则，CSV 数据将以字符串格式返回。
data = {'Name': ['Smith', 'Parker'], 'ID': [101, 102], 'Language': ['Python', 'JavaScript']} 
info = pd.DataFrame(data) 
print('DataFrame Values:\n', info) 
#转换为csv数据
csv_data = info.to_csv() 
print('\nCSV String Values:\n', csv_data)  #
指定 CSV 文件输出时的分隔符，并将其保存在 pandas.csv 文件中
csv_data = info.to_csv("C:/Users/Administrator/Desktop/pandas.csv",sep='|')
```

```
自定义函数:
(1) 操作整个 DataFrame 的函数：pipe()
通过给 pipe()函数传递一个自定义函数和适当数量的参数值，从而操作 DataFrme 中的所有元素
def adder(ele1,ele2):
    return ele1+ele2
df = pd.DataFrame(np.random.randn(4,3),columns=['c1','c2','c3'])
#传入自定义函数以及要相加的数值3
df.pipe(adder,3) #
(2) 操作行或者列的函数：apply()
如果要操作  DataFrame 的某一行或者某一列，可以使用 apply() 方法
import pandas as pd
import numpy as np
df = pd.DataFrame(np.random.randn(5,3),columns=['col1','col2','col3'])
df.apply(np.mean)
#默认按列操作，计算每一列均值
print(df.apply(np.mean)) #
(3) 操作单一元素的函数：applymap()
df = pd.DataFrame(np.random.randn(5,3),columns=['col1','col2','col3'])
#自定义函数lambda函数
print(df['col1'].map(lambda x:x*100))
```

```
缺失值处理:
为了使检测缺失值变得更容易，Pandas 提供了 isnull() 和 notnull() 两个函数
df['one'].notnull()
df['one'].isnull()

fillna() 函数可以实现用非空数据“填充”NaN 值
df = pd.DataFrame(np.random.randn(3, 3), index=['a', 'c', 'e'],columns=['one',
'two', 'three'])
df = df.reindex(['a', 'b', 'c'])
print(df)
#用 0 填充 NaN
print (df.fillna(0))

向前和向后填充NA
ffill() 向前填充和 bfill() 向后填充
df = pd.DataFrame(np.random.randn(5, 3), index=['a', 'c', 'e', 'f','h'],columns=['one', 'two', 'three'])
df = df.reindex(['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h'])
print df.fillna(method='ffill')

删除缺失值
df = pd.DataFrame(np.random.randn(5, 3), index=['a', 'c', 'e', 'f','h'],columns=['one', 'two', 'three'])
df = df.reindex(['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h'])
print(df)
#删除缺失值
print (df.dropna())
```



```
分组:
使用 groupby() 可以沿着任意轴分组。
df.groupby("key")
df.groupby("key",axis=1)
df.groupby(["key1","key2"])
eg：
data = {'Name': ['John', 'Helen', 'Sona', 'Ella'],
   'score': [82, 98, 91, 87],
   'option_course': ['C#','Python','Java','C']}
df = pd.DataFrame(data)
print(df)
#生成分组groupby对象
print(df.groupby('score'))

#查看分组
print(df.groupby('score').groups)

多个列标签分组
#查看分组
print(df.groupby(['Name','score']).groups)

遍历分组
grouped=df.groupby('score')
for label, option_course in grouped:
#其中key代表分组后字典的键，也就是score
    print(label)
#字典对应的值选修的科目

聚合函数
#应用一个聚合函数求均值
print(grouped['score']).agg(np.mean)

通过 filter() 函数可以实现数据的筛选，该函数根据定义的条件过滤数据并返回一个新的数据集。
#定义lambda函数来筛选数据
print (df.groupby('Team').filter(lambda x: len(x) >= 2))
```

```
合并:
merge() 函数参数
left/right	两个不同的 DataFrame 对象。
on	指定用于连接的键（即列标签的名字），该键必须同时存在于左右两个 DataFrame 中，如果没有指定，并且其他参数也未指定， 那么将会以两个 DataFrame 的列名交集做为连接键。
left_on	指定左侧 DataFrame 中作连接键的列名。该参数在左、右列标签名不相同，但表达的含义相同时非常有用。
right_on	指定左侧 DataFrame 中作连接键的列名。
left_index	布尔参数，默认为 False。如果为 True 则使用左侧 DataFrame 的行索引作为连接键，若 DataFrame 具有多层
索引(MultiIndex)，则层的数量必须与连接键的数量相等。
right_index	布尔参数，默认为 False。如果为 True 则使用左侧 DataFrame 的行索引作为连接键。
how	要执行的合并类型，从 {'left', 'right', 'outer', 'inner'} 中取值，默认为“inner”内连接。
sort	布尔值参数，默认为True，它会将合并后的数据进行排序；若设置为 False，则按照 how 给定的参数值进行排序。
suffixes	字符串组成的元组。当左右 DataFrame 存在相同列名时，通过该参数可以在相同的列名后附加后缀名，默认为('_x','_y')。
copy	默认为 True，表示对数据进行复制。

在单个键上进行合并操作:
left = pd.DataFrame({ 
   'id':[1,2,3,4], 
   'Name': ['Smith', 'Maiki', 'Hunter', 'Hilen'], 
   'subject_id':['sub1','sub2','sub4','sub6']}) 
right = pd.DataFrame({ 
    'id':[1,2,3,4], 
   'Name': ['William', 'Albert', 'Tony', 'Allen'], 
   'subject_id':['sub2','sub4','sub3','sub6']})
#通过on参数指定合并的键
print(pd.merge(left,right,on='id'))

通过how参数可以确定 DataFrame 中要包含哪些键，如果在左表、右表都不存的键，那么合并后该键对应的值为 NaN:
left	LEFT OUTER JOIN	使用左侧对象的key
right	RIGHT OUTER JOIN	使用右侧对象的key
outer	FULL OUTER JOIN	使用左右两侧所有key的并集
inner	INNER JOIN	使用左右两侧key的交集

#以left侧的subject_id为键
print(pd.merge(left,right,on='subject_id',how="left"))

outer join(并集):
#求出两个subject_id的并集，并作为键
print(pd.merge(left,right,on='subject_id',how="outer"))

inner join(交集):
#求出两个subject_id的交集，并将结果作为键
print(pd.merge(left,right,on='subject_id',how="inner"))

当 a 与 b 进行内连操作时 a.join(b) 不等于 b.join(a)。
```

```
concat() 函数用于沿某个特定的轴执行连接操作。
参数:
objs	一个序列或者是Series、DataFrame对象。
axis	表示在哪个轴方向上（行或者列）进行连接操作，默认 axis=0 表示行方向。
join	指定连接方式，取值为{"inner","outer"}，默认为 outer 表示取并集，inner代表取交集。
ignore_index	布尔值参数，默认为 False，如果为 True，表示不在连接的轴上使用索引。
join_axes	表示索引对象的列表。

import pandas as pd
a= pd.DataFrame({'A': ['A0', 'A1', 'A2', 'A3'],
                    'B': ['B0', 'B1', 'B2', 'B3'],
                    'C': ['C0', 'C1', 'C2', 'C3'],
                    'D': ['D0', 'D1', 'D2', 'D3']},
                    index=[0, 1, 2, 3])
b= pd.DataFrame({'A': ['A4', 'A5', 'A6', 'A7'],
                    'B': ['B4', 'B5', 'B6', 'B7'],
                    'C': ['C4', 'C5', 'C6', 'C7'],
                    'D': ['D4', 'D5', 'D6', 'D7']},
#连接a与b
print(pd.concat([a,b]))

如果想把指定的键与 DataFrame 对象连接，您可以使用 keys 参数来实现
#连接a与b,并给a，b连接一个指定的键
print(pd.concat([a,b],keys=['x','y']))

如果想让输出的行索引遵循依次递增的规则，那么需要将 ignore_index 设置为 True 
#连接a与b,设置 ignore_index 等于 True
print(pd.concat([a,b],keys=['x','y'],ignore_index=True))

如果您想要沿着 axis=1 添加两个对象，那么将会追加新的列。

#沿着 axis=1，连接a与b
print(pd.concat([a,b],axis=1))

append()可以使用
```


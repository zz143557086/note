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
可以将行标签传递给 loc 函数 iloc 允许接两个参数分别是行和列，参数之间需要使用“逗号”隔开，但该函数只能接收标签索引。
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
info 返回不为空的行数
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








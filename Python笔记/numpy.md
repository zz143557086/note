1.numpy.array 

```python
 
numpy.array(object, dtype = None, copy = True, order = None, subok = False, ndmin = 0)
 #object 任何暴露数组接口方法的对象都会返回一个数组或任何（嵌套）序列。
 #dtype 数组的所需数据类型，可选。
 #copy 可选，默认为true，对象是否被复制。
 #order C（按行）、F（按列）或A（任意，默认）。
 #subok 默认情况下，返回的数组被强制为基类数组。 如果为true，则返回子类。
 #ndmin 指定返回数组的最小维数。
 
# 最小维度  
import numpy as np 
a = np.array([1,  2,  3,4,5], ndmin =  2)  
print a
#结果 [[1, 2, 3, 4, 5]]
 
# dtype 参数  
import numpy as np 
a = np.array([1,  2,  3], dtype = complex)  
print a
#结果 [ 1.+0.j,  2.+0.j,  3.+0.j]
```

2.numpy.dtype(object, align, copy)

```python
Object：被转换为数据类型的对象。
Align：如果为true，则向字段添加间隔，使其类似 C 的结构体。
Copy ? 生成dtype对象的新副本，如果为flase，结果是内建数据类型对象的引用。
```

3.`ndarray.shape ` 这一数组属性返回一个包含数组维度的元组，它也可以用于调整数组大小。

```python
import numpy as np 
a = np.array([[1,2,3],[4,5,6]])  
print a.shape
#结果(2, 3)
# 这会调整数组大小  
import numpy as np 
a = np.array([[1,2,3],[4,5,6]]) a.shape =  (3,2)  
print a 
#结果 [[1, 2] [3, 4] [5, 6]]
#NumPy 也提供了reshape函数来调整数组大小。
import numpy as np 
a = np.array([[1,2,3],[4,5,6]]) 
b = a.reshape(3,2)  
print b
#结果[[1, 2] [3, 4] [5, 6]]
```

4.`ndarray.ndim  `这一数组属性返回数组的维数。

5.`numpy.itemsize` 这一数组属性返回数组中每个元素的字节单位长度。

6.`numpy.zeros` 返回特定大小，以 0 填充的新数组。

```
numpy.zeros(shape, dtype = float, order = 'C')
#Shape 空数组的形状，整数或整数元组
#Dtype 所需的输出数组类型，可选
#Order 'C'为按行的 C 风格数组，'F'为按列的 Fortran 风格数组
```

7.`numpy.ones`  返回特定大小，以 1 填充的新数组。

8.`numpy.arange`这个函数返回`ndarray`对象，包含给定范围内的等间隔值。

```
numpy.arange(start, stop, step, dtype)
import numpy as np
x = np.arange(5)  
print x
#结果 [0  1  2  3  4]
```

9.`numpy.linspace`

```
import numpy as np
x = np.linspace(10,20,5)  
print x
#结果 [10.   12.5   15.   17.5  20.]
```

10.高级索引

```python
x[行，列]
x[1:3,2:3] #前俩行第二列
```

11.布尔索引

```python
x[x>5]#大于5的元素
```

12.`numpy.append`

```python
numpy.append(arr, values, axis)
#arr：输入数组
#values：要向arr添加的值，比如和arr形状相同（除了要添加的轴）
#axis：沿着它完成操作的轴。如果没有提供，两个参数都会被展开。 
import numpy as np 
a = np.array([[1,2,3],[4,5,6]]) 
print '第一个数组：' 
print a 
print '\n'  
print '向数组添加元素：' 
print np.append(a, [7,8,9]) 
print '\n'  
print '沿轴 0 添加元素：' 
print np.append(a, [[7,8,9]],axis = 0) 
print '\n'  
print '沿轴 1 添加元素：' 
print np.append(a, [[5,5,5],[7,8,9]],axis = 1)
#结果  
第一个数组：
[[1 2 3]
 [4 5 6]]
向数组添加元素：
[1 2 3 4 5 6 7 8 9]
沿轴 0 添加元素：
[[1 2 3]
 [4 5 6]
 [7 8 9]]
 沿轴 1 添加元素：
[[1 2 3 5 5 5]
 [4 5 6 7 8 9]]
```

13.`numpy.insert`

```python
 numpy.insert(arr, obj, values, axis
#arr：输入数组
#obj：在其之前插入值的索引
#values：要插入的值
#axis：沿着它插入的轴，如果未提供，则输入数组会被展开
```

14.arr.num()  求数组中数的和
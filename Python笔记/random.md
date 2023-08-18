1. random.randint(1,10)

   生成1到10的随机数

2. random.random()

   生成0到1之间的浮点数

3. random.unform(n,m)

   生成n到m之间的浮点数

4. random.randrange(n,m,k)

   产生从n---m间隔为k的整数

5. random.choice([1, 2, 3, 4, 5, 6, 7, 8, 9, 0])

   从序列中随机选取一个元素

6. random.shuffle([1,3,5,6,7])

   在一些特殊的情况下可能对序列进行一次打乱操作

7. 需要先导入 import random

8. random.sample(list1.num)

   可以从指定的序列中，随机的截取指定长度的片断，不作原地修改。

9.numpy 中的一些应用

```python
first = np.random.random(n)   #生成n个随机数
red=np.round(first*(mony/first.sum()),2)    #对随机数做出调整，使和为mony#设定随机数精确至小数点后两位
```

10 round(a,b)

a 需要进行四舍五入的数字。
b 指定的位数，按此位数进行四舍五入

##### 11.random.seed()  使得随机数据可预测，即只要seed的值一样，后续生成的随机数都一样。

```python
>>> import random
>>> random.seed(1)
>>> x=[random.randint(1,5) for i in range(5)]
>>> x
[1, 5, 4, 2, 3]
>>> x=[random.randint(1,5) for i in range(5)]
>>> x
[3, 4, 4, 1, 1]
>>> random.seed(1)
>>> y=[random.randint(1,5) for i in range(5)]
>>> y
[1, 5, 4, 2, 3]
random.seed() 没有返回值，print为None,
如果不设定seed的话，python会自动选择seed，生成的random会发生变化。
如果设定相同的seed，则每次结果都相同。
```


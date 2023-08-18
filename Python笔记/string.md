```python
#f string 将变量替换到字符串中
a = "12"
#特殊 f"da={a}"
```



##### 1.replace

```python
str.replace(old, new[, max])
# old：将要被我们替换的旧的字符串
# new：新字符串，用来替换旧的字符串（替换一次或者多次old）
# max：用来替换的次数 不输入为全部替换
```

2.isdecimal():判断给定字符串是否全为数字

3.isalpha():判断给定的字符串是否全为字母

4.isalnum()：判断给定的字符串是否只含有数字与字母

5.isupper():判断给定的字符串是否全为大写

6.islower():判断给定的字符串是否全为小写

7.istitle():判断给定的字符串是否符合title()

8.isspace():判断给定的字符串是否为空白符（空格、换行、制表符）

9.isprintable():判断给定的字符串是否为可打印字符（只有空格可以，换行、制表符都不可以）

##### 10.isidentifier():判断给定的字符串是否符合命名规则（只能是字母或下划线开头、不能包含除数字、字母和下划线以外的任意字符。）

##### 11.**string.strip(s[, chars]) ** #删除前导和后缀字符  如果strip()的参数为空，那么会默认删除字符串头和尾的空白字符(包括\n，\r，\t这些) 

#####  12.lstrip()和rstrip()这两个函数和上面的strip()基本是一样的，参数结构也一样，只不过一个是去掉左边的(头部)，一个是去掉右边的(尾部)。

##### 13.split  str.split(str="",num=string.count(str))[n] 

```python
 str： 表示为分隔符，默认为空格  num：表示分割次数  num：表示分割次数
 s= 'www.dod.com.cn'
print(s.split()) # 默认分隔符
print(s.split('.')) #  . 分割
print(s.split('.',1))  #  分割一次   2次
print(s.split('.',2))
print(s.split('.',2)[1]) # 取出被 . 分割的下标为1的字符串
print(s.split('.',-1)) # 分割最多次实际与不加参数一样（默认分割富一样）
s1,s2,s3= s.split('.',2) #分割三次并将分割的字符串保存到三个文件内
print(s1)
print(s3)
print(s2)
# 去掉换行符  \n  \t
c = '''hello
    world'''
print(c)
print(c.split('\n'))
print(c.split('\t'))
# 分离文件名和路径
#os.path.split()：按照路径将文件名和路径分割开
import  os
print(os.path.split('/dodo/soft/python/'))
print(os.path.split('/dodo/soft/python'))
#超级实例列举
a= 'hello boy<[www.dodo.com.cn]>byebye'
# 已[分割
print(a.split('['))
# 以【分割后取值下标为1的值，然后再次已】分割取下标为0的值
print(a.split('[')[1].split(']')[0])
# 以【分割后取值下标为1的值，然后再次以】分割取下标为0的值在次以。分割
print(a.split('[')[1].split(']')[0].split('.'))
```

string.ascll_letters  打印出所有大小写字符

string.ascll_uppercase 大写字母

sting.ascll_lowercase 小写字母

string.punctuation 特殊字符

string.digits 数字
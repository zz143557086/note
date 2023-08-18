#### 导入：from bs4 import BeautifulSoup

**requests或者urllib2来打开一个网址**

```python
import requests
url = "https://www.baidu.com"
r1 = requests.get(url,'lxml')
r1.encoding='utf-8'
#print (r1.text)
```

**创造一个BeautifulSoup对象**

```python
bs_1=BeautifulSoup(r1.text,'lxml')
#print(bs_1)
两个参数：第一个参数是要解析的html文本，第二个参数是使用那种解析器，对于HTML来讲就是html.parser，这个是bs4自带的解析器。
解析器	使用方法	优势
python标准库	BeautifulSoup(html, “html.parser”)	1、Python的内置标准库2、执行速度适中3、文档容错能力强
lxml HTML	BeautifulSoup(html, “lxml”)	1.速度快2.文档容错能力强
lxml XML	BeautifulSoup(html, [“lxml”, “xml”]) BeautifulSoup(html, “xml”)	1.速度快2.唯一支持XML的解析器
html5lib	BeautifulSoup(html, “html5lib”)	1.做好的容错性2.以游览器的方式解析文档3.生成HTML5的文档
```

**通过这个对象来实现对获取到的源码进行筛选和处理**

```python
print(bs_1.prettify()) #格式化输出全部内容
print(bs_1.标签名)
#标签名有html,head,title,meta,body,script,style等等
```

# BeautifulSoup四大对象种类

- **Name** ：每个 tag 都有自己的名字

```python
tag.name
# 'head'
```

- **Attributes**：tag 的属性是一个字典

```python
tag['class']
# 'boldest'
tag.attrs
# {'class': 'boldest'}
type(tag.attrs)
# <class 'dict'>
```

- **多值属性**：最常见的多值属性是class，多值属性的返回 list

```python
soup = BeautifulSoup('<p class=""></p>')
print(soup.p['class'])  # ['body', '']
print(soup.p.attrs)     # {'class': ['body', 'aaa']}
```

如果某个属性看起来好像有多个值,但在任何版本的HTML定义中都没有被定义为多值属性，那么Beautiful Soup会将这个属性作为字符串返回。

```python
a1 = BeautifulSoup('<p id="my id"></p>', 'html.parser')
print(a1.p['id'])    # 'my id'
```

**Text**：返回 tag 的所有字符串连成的字符串

- **其他方法**

```python
tag.has_attr('id')  #返回 tag 是否包含 id 属性
```

## NavigableString

字符串常被包含在 tag 内，Beautiful Soup 用 NavigableString 类来包装 tag 中的字符串。但是字符串中不能包含其他 tag。

```python
a1 = BeautifulSoup('<b class="aaa">bbb</b>')
s = a1.b.string
print(s)        # bbb
print(type(s))  # <class 'bs4.element.NavigableString'>
```

## BeautifulSoup

BeautifulSoup 对象表示的是一个文档的全部内容。大部分时候，可以把它当作 Tag 对象。但是 BeautifulSoup 对象并不是真正的 HTM L或 XML 的 tag，它没有attribute属性，name 属性是一个值为“[document]”的特殊属性。

## Comment comment一般表示文档的注释部分

```
a1 = BeautifulSoup("<b><!--This is a comment--></b>")
comment = a1.b.string
print(comment)          # This is a comment
print(type(comment))    # <class 'bs4.element.Comment'>
```

# CSS选择器

标签名不加任何修饰，类名前加点，id名前加#，在这里用的方法大致是一样的，用到的方法是bs_1.select(),它的返回值是一个列表list

通过标签名字

```python
print bs_1.select('title')
```

通过类名

```python
print bs_1.select('.class')
```

通过id

```python
print bs_1.select('#a_1')
```

**组合查找** 这里和在写css的格式是一样的

```python
print bs_1.select('.class #id')
#意思是查找.class类下的id是id的元素
```

**子查询**

```python
print bs_1.select('head > title')
```

**属性查找**

```python
print bs_1.select(p[class="new"])
```


### urllib.request 请求模块

#### 1.urlopen()函数的使用

创建一个表示远程url的类文件对象，然后像本地文件一样操作这个类文件对象来获取远程数据。

```python
from urllib import request
resp = request.urlopen('https://www.baidu.com/')
print(resp.read())
# """"""urlopen(url, data)
1、参数：url（请求的url，即字符串网址），data（如果设置了这个值，那么将变成post请求）。
2、返回值：返回一个http.client.HTTPResponse对象，这个对象是一个类文件句柄对象，有read(size)、readline、readlines及getcode等方法。

```

#### 2.urlurlretrieve()函数的使用

```python
from urllib import request
request.urlretrieve('https://www.baidu.com/', r'F:\开发工具\python\project\爬虫\爬虫基本库的使用\baidu.html')
#urlretrieve(url, file)
1、参数：url（请求的url，即字符串网址），file（获取文件的保存路径）。
```

#### 3.request.Request 类的使用

如果想要在请求的时候添加一个请求头，就必须要使用此类，例如在不添加User-Agent的时候无法爬取百度的HTML文件，如果添加上User-Agent，那么就可以轻而易举的爬取到百度首页的HTML文件：

```python
from urllib import request

url = 'https://www.baidu.com/'
headers = {
    'User-Agent': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/87.0.4280.88 Safari/537.36'
}
rq = request.Request(url, headers=headers)
resp = request.urlopen(rq)
print(resp.read())
```

### urllib.parse 解析模块

#### 1.urlencode()和parse_qs()函数的使用

urlencode()是将字典数据转换为URL编码数据，parse_qs()是将经过编码后的URL数据解码。

```python
from urllib import parse
dic = {'name':'晴朗', 'age':18, 'sex':'mail'}
qs = parse.urlencode(dic)
print(qs)  #name=%E6%99%B4%E6%9C%97&age=18&sex=mail
print(parse.parse_qs(qs))  #{'name': ['晴朗'], 'age': ['18'], 'sex': ['mail']}
```

#### 2.urlsplit()和urlparse()函数的使用

两者的作用都是对url进行解析，唯一不一样的地方是urlparse里面有params属性，而urlsplit里面没有这个属性。

```
from urllib import parse
url = 'https://www.baidu.com/index.html;user?id=S#comment'
res1 = parse.urlsplit(url)
res2 = parse.urlparse(url)
print(res1)
# SplitResult(scheme='https', netloc='www.baidu.com', path='/index.html;user', query='id=S', fragment='comment')
print(res2)
# ParseResult(scheme='https', netloc='www.baidu.com', path='/index.html', params='user', query='id=S', fragment='comment')
```


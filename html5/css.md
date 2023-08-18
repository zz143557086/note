#### 1.font-family（字体），color（颜色），和font-size（字体大小）属性来定义字体 background-color 背景颜色

```html
<h1 style="font-family:verdana;">一个标题</h1>
<p style="font-family:arial;color:red;font-size:20px;">一个段落。</p>
文本对齐属性 text-align取代了旧标签 <center> 。
```

2.可以在<head> 部分通过 <style>标签定义内部样式表

```html
<head>
<style type="text/css">
body {background-color:yellow;}
p {color:blue;}
</style>
</head>
```

3.外部样式表

```html
<head>
<link rel="stylesheet" type="text/css" href="mystyle.css">
</head>
```

4.
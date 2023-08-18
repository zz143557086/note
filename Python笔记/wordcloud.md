1.wordcloud 必写步骤

```python
 import wordcloud #提供函数库
 c = wordcloud.WordCloud() #生成词云对象
 c.generate("wordcloud by Python") #加载词云文本
 c.to_file("pywordcloud.png") #输出图片文件
```


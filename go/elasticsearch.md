#### mysql搜索面临的问题

```
1.性能低下
2.没有相关性排名-刚需 like搜索的时候无法根据相关度高进行排序
3.无法全文搜索
4.搜索不准确-没有分词功能 
```

#### 什么是elasticsearch

```
elasticsearch是一种分布式可扩展的实时搜索和分析引擎
分布式实时文件存储,并将每一个字段都编入索引，使其可以被搜索
实时分析的分布式搜索引擎
可以扩展到上百台服务器，处理PB级别的结构化或非结构化数据

总结:分布式全文搜索引擎
```

#### mysql和es

```
table->index row->document column->field schema(类型 长度)->mapping sql->DSL
```

#### 索引

```
有两个含义:动词(insert),名词(表)
elasticsearch将它的数据存储到一个或者多个索引(index)中，索引就像数据库,可以向索引写入文档或者从索引中读取文档
```

#### 



















match查询(匹配查询)

```

```

match_phrase查询(精准查询)
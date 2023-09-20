#### redis基本了解

```
redis的键是区分大小写的
redis默认字符串存储数据而且是二进制安全的 默认不支持中文
quit 退出
redis-cli --row 以原生的形态显示 支持中文
```

#### 字符串及基本命令

```
字符串 string
set key value 保存键值
get key 获取键值
del key 删除一个键
exists key 判断键是否存在
keys * 查找所有的键
keys *lin 查找所有以lin结尾的键类似% 
flushall 删除所有的键
ttl key 查看键的过期实间 -1表示没有设置 -2表示已经过期了
expire key time 设置键的过期时间
setnx key value 键不存在时设置值 存在不做任何动作
```

#### 列表及基本命令

```
列表 list 类似数组 列表中元素都是可以重复的
lpush key a 将元素添加到头部 rpush lkey a将元素添加到尾部
lrange key 0 -1 获取从左开始第一个到最后一个元素 -1表示最后一个元素
rpop key count 从列表的尾部删除元素个数
lpop key count 从列表的头部删除元素个数
llen key 查看列表的长度
ltrim key 1 3 删除1到3以外的元素
lrem key 1 3 删除1到3的所有元素
```

#### 集合及基本命令

```
集合 set  集合中元素都是不可重复的
sadd key value... 表示要添加到元素到集合key 元素可以有多个
smembers key 查看集合key中的元素
sismember key value 判断元素是否在集合key中 1表示在0表示不在
srem key value 要删除集合中的元素
```

#### 有序集合

```
有序集合 SortedSet 集合中每个元素都会关联一个浮点分数 元素顺序按照分数从小到大排序 分数可以重复的
zadd key （score name）... 分数和名称为一个元素添加到集合key可以添加多个
zrevrank key 0 -1 输出所有成员 逆序排名（即排名从大到小）加上 withscores则是输出分数
zrange key name 查找 该成员在集合中的index
```

#### 哈希 Hash

```
hset key (field value)... 添加键值对到哈希表key中
hget key field 通过字段获取值
hgetall key 获取哈希表中所有的键值对
hdel key field 通过字段删除键值对
hexists key filed 判断某个键值对是否存在
hkery key 获取哈希表中的所有键值对
hlen key 获取哈希表key键值对数量
```

#### 发布订阅

```
subscribe key... 订阅一个或多个频道 
publish key message 在频道key发布message  消息无法持久化
```

#### 消息队列 Stream

```
xadd key id filed value 添加一个name消息有id(可以*随机生成一个id) 消息为filed为value
xlen key 查看消息数量
xrange key - + 表示查看所有信息
xdel key id 删除该id消息
xtrim key maxlen 0 删除所有消息
xread count num block time streams key 0 从key中从头读取num条消息没有消息就杜塞time毫秒 获取从现在开始到最新的消息把0改成$
xgroup create key groupname id 创建一个消费者组
xinfo groups key 查看消费者组的信息
xreadgroup croup groupname count num  block time streams key> 读取消费者组的groupname的消息一次num条消息 没有收到消息就杜塞time毫秒 >表示从这个消息中读取最新消息
```

事务

```
multi事务的开始
逻辑处理 
exec 提交事务 discard
redis不能保证事务的逻辑处理保持一致性
redis可以保证1.在发生exec命令前所有命令都在一个队列中，不会立即执行2.不会因为某一个命令执行失败导致其他命令不会执行3.在事务的执行命令中其他命令不会插入到事务的执行命令
```

持久化

```
RDB 在指定时间间隔内将内存的数据写入磁盘时候做备份 可以使用save进行保存
AOF 以日志的形式记录每一个写操作
```

主从复制



```
主节点负责写操作 主节点会将数据变化通过异步的方式发给从节点
从节点负责读操作 从节点接收到主节点数据后更新自己的数据
```



```
地理位置 Geospatial

HyperLogLog

位图 Bitmap

位域 Bitfield
```


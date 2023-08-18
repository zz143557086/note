```
验证身份使用json的 web_token
x-token 是加密的不能被反解 每一个微服务都能够解密
由三部分构成 1.header token类型和算法 2.payload  自己定义的内容3.signature 根据密钥生成的签名
将需要缓存在header的数据放入createToke(data)创建token
// 将claims设置到gin的上下文中，以便后续处理程序可以使用
	c.Set("claims", claims)
	c.Set("userId", claims.ID)
```

```
session 将缓存信息存储再服务器 用于保存敏感或重要的用户数据
cookie 将缓存信息存储在客服端 用于存储一些较为简单的用户信息
```


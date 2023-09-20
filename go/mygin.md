##### gin的使用过程

```
1.创建路由
r:=gin.Default() 
//默认的路由使用了 logger日志中间件 记录每一个请求的信息 比如路由地址,请求方法,打印实际
Recovery 中间件：在发生 panic 异常时，会恢复程序运行并返回一个 500 内部服务器错误的响应。这个中间件可以保障应用程序的稳定性，避免由于异常导致整个应用崩溃。
2.注册处理函数到路由和中间件
创建路由组v:=r.Group("/v1")
中间件的使用 v.use(cors) 中间本质是一个gin.HandlerFunc 接收一个context参数 c.get获取上文的设置的参数 也可以c.set设置参数到下文 进行本地验证再确定下文是否进行 不进行使用c.abort到一个index最大的中间件为空结束请求 进行使用c.next进行下一个中间件或者处理函数
什么方式的路由 路由地址 客服端请求的处理 eg:v.get("/user/list",list)
3.启动服务r.run(ip:port)监听的端口号

1.其中参数校验 定义个form文件里面放校验的表单结构使用tag binding 验证数据格式 c.ShouldBindJSON(form表)来验证
2.如果是用户验证 使用jwt中间件 看请求的header里是否有x-token是否有用户信息 jwt再完成解析后会把用户信息c.set给下文


get获取检索 post创建 delete删除 put全部修改 patch部分修改
```

**Context之间的关系，是一颗树形结构，父Context消亡后，子Context会自动消亡。**

**准确说它是 goroutine 的上下文，包含 goroutine 的运行状态、环境、现场等信息。**

**context 主要用来在 goroutine 之间传递上下文信息，包括：取消信号、超时时间、截止时间、k-v 等。**

**main.go 就是这颗树的根Context节点，称之为background**

**handler方法的第一参数必须为Context类型**

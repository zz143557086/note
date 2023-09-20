### 1. New 一个Engine实例

```go
app := gin.Default()
/*默认的路由使用了 logger日志中间件 记录每一个请求的信息 比如路由地址,请求方法,打印实际
Recovery 中间件：在发生 panic 异常时，会恢复程序运行并返回一个 500 内部服务器错误的响应。这个中间件可以保障应用程序的稳定性，避免由于异常导致整个应用崩溃。*/
```

### 2. 注册处理函数到路由、中间件

你可能会疑惑，为什么这里的路由处理函数要接受一个 gin.Context 类型的参数，是在何时传入的？

**Engine结构体本身发挥的核心功能就是路由处理。**

```go
app.GET("/ping", func(c *gin.Context) {
        c.JSON(200, gin.H{
            "message": "pong",
        })
    })
```

### 3. 启动Gin框架

**Run 本质就是将 注册的路由信息engine 绑定到一个 http.Server，然后开始开始监听并处理请求**

```go
app.Run()
```

**Context之间的关系，是一颗树形结构，父Context消亡后，子Context会自动消亡。**

**准确说它是 goroutine 的上下文，包含 goroutine 的运行状态、环境、现场等信息。**

**context 主要用来在 goroutine 之间传递上下文信息，包括：取消信号、超时时间、截止时间、k-v 等。**

**main.go 就是这颗树的根Context节点，称之为background**

**handler方法的第一参数必须为Context类型**


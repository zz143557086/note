### 容器理解

```
每一个容器看作是一个简易版的linux环境 即linux内核心
docker 的容器层是可读可写的
当容器启动时,一个新的可写层被加载到镜像的顶层 这一层被称为容器层 容器层一下都是镜像层
```

### 新建和启动容器

```
docker run [option] 镜像名称 命令 以及其他的参数选项
option说明
 a:--name="容器新名字" 为容器指定一个名称
 b:-d 后台运行容器并返回容器ID,也即启动守护式容器
 c:-i 一交互模式运行容器,通常与-t同时使用
 d:-t 为容器重新分配一个伪输入终端,通常与-i同时使用 即启动交互式容器(前台有伪装端,等待交互) /bin/bash 希望有个交互式的shell  退出 exit
 e:-P随机端口映射 大写P
 f:-p指定端口映射 小写p
```

### 列出容器和退出容器和启动停止运行的容器

```
1.docker ps [option] 列出当前正在运行的容器
 a:-a 列出当前正在运行+历史运行过的
 b:-l 显示最近创建的容器
 c:-n x 显示最近创建的x个容器
 d:-q 静默模式,只显示容器编号
2.2种退出方式
 a:run进去容器,exit退出，容器停止
 b:run进去容器，ctrl+p+q退出，容器不停止
3.docker start 容器ID或者容器名 启动容器
4.docker restart 容器ID或者容器名 重启容器
5.docker stop 容器ID或者容器名 停止容器
6.docker kill 容器ID或者容器名 强制停止容器
7.docker rm 容器ID 删除已经停止的容器 -f强制删除
```

### 后台运行容器

```
1.docker logs 容器id 查看容器日志
2.docker top 容器id  查看容器进程详情
3.docker inspect 容器id 查看容器内部细节
4.重新进入容器以命令行交互
docker exec -it 容器ID /bin/bash //exec 用于执行正在运行的容器  exit不会退出
docker attach  容器ID /bin/bash  //exit会退出
```

### 容器内拷贝文件到主机

```
1.docker cp 容器id:容器内路径 目的主机路径 拷贝
2.docker export 容器id >导出文件压缩包 导出容器
3.cat 文件名.tar|docker import - 镜像用户/镜像名:镜像版本号  导入容器
```

### 容器提交

```
1.docker commit 提交容器副本使之成为一个新的镜像
2.docker commit -m ="提交的描述信息" -a="作者" 容器id要创建的目标镜像名[:标签名]
```


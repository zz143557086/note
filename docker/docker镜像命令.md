### 镜像理念 镜像分层

```
镜像是一种轻量级可执行的软件包 类似安装包 
我们把应用程序和配置依赖打包形成一个可交付的运行环境 这个打包好的环境就是image镜像文件
Union文件系统是docker镜像的基础 镜像可以通过分层来进行继承 docker镜像是由一层一层的文件系统组成
镜像分层好处共享资源 为方便复制迁移 提供复用 
比如说多个镜像都是从 相同的base镜像构建来 那么Docker Host只需要在磁盘保存一份base镜像
docker 镜像层都是只读的
```

### 启动命令

```
1.systemctl start docker 启动docker
2.systemctl stop docker 停止docker
3.systemctl restart docker 重启docker
4.systemctl status docker 查看docker状态
5.systemctl enable docker 开机启动
6.docker info 查看docker概要信息
7.docker --help 查看docker帮助文档
8.docker 具体命令 --help 查看docker命令帮助文档
```

### 镜像命令

##### 列出镜像

```
docker images 列出本地主机上的镜像
 a：-a 列出本地所有镜像(含历史镜像)
 b：-q 只显示镜像ID
选项说明
 a：REPOSITORY 表示镜像的仓库源
 b：TAG 镜像的标签版本号
 c：IMAGE ID 镜像id
 d：CREATED 镜像创建时间
 e：SIZE 镜像大小
```

##### 查找镜像

```
 docker search [option]镜像名称 查找镜像
 option说明
 --limit n :只列出n个镜像 默认25个
 选项说明
 a：NAME 镜像名称
 b：descrip 镜像说明
 c：start 点赞数量
 d：official 是否是官方的
 e：automoted 是否是自动构建的
 网站 https://hub.docker.com 查询镜像
```

##### 下载镜像和查看镜像以及删除镜像

```
1.docker pull 镜像名字[:TAG]  下载镜像
没有TAG就是最新版本
2.docker system df 查看镜像/容器/数据卷所占的空间
3.docker rmi 镜像名(镜像id) 删除镜像 -f强制删除
4.docker rmi -f $(docker images -qa) 全部删除
```

### 面试题

```
1.谈谈什么是docker的虚悬镜像 
有大小 有id  仓库名，标签都是none的镜像
```


### git 文件拉取修改以及提交

```
git clone url 克隆远程项目到本地
git status 查看版本库中文件的修改状态
git add [被修改的文件] 
git add . 自动找到本目录下被修改的文件 
git commit 保存修改到本地库 -m "提交内容"直接修改
git remote [选项] 设置或读取与远程仓库相关的内容
git push 推送修改到远程仓库
git config --local user.name 'abc' 配置本地用户
git config --local user.email 'abc@163.com' 配置本地用户的邮箱 
git log 查看日志
```

### 文件的恢复

```
从版本库恢复文件
三种情况
已删除(或修改),未add  
git checkout {文件路径} 
已删除(或修改),add未commit
git checkout {文件路径} 修改的次数的标记符
已删除(或修改),已commit
git checkout {文件路径} 修改的次数的标记符
检出:git checkout

执行add是将工作区的内容放入暂存区 执行commit是吧暂存区的内容放入版本库
git checkout是将暂存区恢复到工作区
```

### 分支管理

```
分支管理
在开发分支上进行修改之后合并到产品线
1.创建分支
git init -b dev 创建版本库的同时创建分支
git branch 分支名称 在当前版本库创建一个分支
git branch -m 原分支名 新分支名 分支重命名 -m就是移动
2.查看分支
git branch
3.删除分支
git branch -d 分支名称 删除已经合并的分支  -D强制删除分支
4.git checkout 分支名称切换到分支
5.git push --set-upstream origin dev 将分支设置为上游分（即追踪）分支
6.git merge <被和并的分支>  将一个分支和并到当前分支
7.git checkout -b 切换创建分支名称  创建并且到分支
```

### 关联远程仓库

```
关联远程仓库
git remote add 远程库名称 远程库地址  
git push -u 远程库名称 本地分支  -u将本地的分支合并到远程分支
git remote show 显示关联的远程仓库 远程仓库管理操作
```


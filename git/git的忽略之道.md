### gitgnore规则

```
git的忽略之道
创建 vim.gitignore
.gitignore 配置git忽略的文件
使用 在项目根目录创建一个.gitignore的文件对下级目录进行版本控制

模式匹配
空行不匹配任何内容仅仅作为分隔符
#用于注释 
\ 用于转译
* 可以用于匹配任何内容(0次或者多次)
？可以匹配任何字符(1次) 都不能匹配/
/用于分割目录 
 a：在开头表示从.gitignore文件所在的目录开始匹配 否则所有的下级都会被匹配
 b：在结尾，只匹配目录，否则，则同名的目录和文件都会被匹配
!否定的以上 使用！改文件会被重新包含 如果文件的父目录被排除也不会被重新包含
[] 通常用于匹配一个字符列表,比如a[mn]z 可匹配amz 和anz
** 用于匹配多级目录，如a/**/b 可匹配 "a/b" ,”a/x/b","a/x/y/b"

使用
 忽略所有的内容
 *
 忽略所有的目录
 */
 忽略pubulic目录下的所有文件 除了a.ico
 public/*
 !public/a.ico
 只保留public目录下的a(一个字符)z.(后缀名)的所有文件
 /*
 !/public
 /public/*
 !/public/a?z.*
```

### gitignore查看

```
git check-ignore {文件或目录路径} 文件或者目录是否被忽略掉
git check-ignore -v{文件或目录路径} 忽略掉生效的具体命令
gitignore 文件只能忽略那些没有被追踪的文件
解决方法:
git rm -r -cached 清除本地缓存
git add 添加
git status 查询状态
已被.gitgnore忽略的文件也是无法加入版本库的
解决方法:
移除规则
```


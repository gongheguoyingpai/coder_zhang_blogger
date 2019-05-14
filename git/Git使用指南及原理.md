# Git使用指南及原理

### 分支操作
- 查看当前工作区所在分支
```
git branch
```
- 查看远程服务器所有分支
```
git branch -a
```
- 切换分支
```
git checkout 分支名
```
- 检出远程分支
```
git checkout 本地分支名 origin/远程分支名
```

### git日志查看
- git查看提交日志
```
git log
```
- git查看指定条数的日志
```
git log -n
```

### git查看提交内容
```
git show COMMIT编号
```

### git回撤操作
- git回撤本地未提交的操作
```
git checkout file_path
```
- git回撤本地已经提交的操作
```
git reset HEAD^    # 回撤到上一个版本
```
- git回撤本地已经提交的某个文件
```
git reset HEAD^ file_path   # 回撤某个文件到上一个版本
```
- git将本地状态回退到和远程一样
```
git reset --hard origin/master
```
- git回退到某个版本
```
git reset 版本号
```

### 其他操作
- git建立本地仓库
```
git init
```
- git将本地仓库推送到远程仓库
```
git remote add origin 远程库地址
```
- git忽略掉某些文件
```
在git的项目目录下创建.gitignore文件，并在其中添加要忽略的文件的pattern，比如要忽略掉pyc文件，则可以在.gitignore文件中添加一行
*.pyc
这样git就会忽略掉对pyc后缀文件的检查
```
### 问题
- git中的origin是什么意思?
origin是git默认创建的指向远程代码仓库的标签，因此origin就是默认情况下远端库的名字。
- git中pull和fetch的区别?
pull=fetch+merge，即pull命令会下拉远程分支并且与本地分支合并；fetch只拉取远程分支，但不做合并。

### 参考文章
Git远程操作详解: http://www.ruanyifeng.com/blog/2014/06/git_remote.html

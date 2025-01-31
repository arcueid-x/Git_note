## Git学习笔记

> git help相关

* git help：提供常用的git命令

* git help -a：获得所有子命令列表

* git help -g：获得教程列表

* git help init(子命令)：获取特定子命令说明

* /subcommand：shift+N前进，shfit+Q退出

---

### 使用'git init'创建Git储存库

* git init：用于创建新git存储库的命令。要在新目录中初始化存储库，提供可选路径：

```shell
git init my-git-notes
```

```shell
cd my-git-notes
ls//显示为空
ls -a//会显示隐藏的.git目录
```

> 可以使用ls .git，列出.git目录的内容

```shell
ls .git
```

> 这个就是一个git仓库

---

### Git状态和隐藏的.git目录

> git status使用Git存储库时一直使用的命令

* git status：显示你所在的分支和你提交的历史记录

> 若删除.git文件则，git仓库失效

直接回到方才的目录，运行：

```shell
git init
```

再次创建仓库

---

### 跟踪和暂存文件

* echo：该命令可用于将文本写入新文件

```shell
echo "#git-help" > git-help.txt
echo "#git-init" > git-init.txt
echo "#git-status" > git-status.txt
```

> 当前文件尚未被追踪，因此在git status中查询不到记录

* git add git-help.txt：用git add 文件名 来添加文件

```shell
git add git-help.txt
```

> 此时，githelp尚未提交，只是<font color=#600>暂存</font>准备被提交，其他文件同理

---

### 使用'git reset'优化暂存区域

* git reset 文件名：从缓存区删除文件

* git reset .(点)：删除所有缓存区文件

---

### 为提交设置Git配置

用<font color=#600>config</font>命令设置自己的git配置（在提交之前）

```shell
git config --global user.name "name"//设置自己的name
git config --global user.email "email"//设置自己的邮箱
git config --list//查看自己git配置
```

---

### 了解Git提交、添加和状态

> 用<font color=#600>commit</font>命令提交

*git commit：* 进行提交，*-m* 添加消息

```shell
git commit -m "describe"
```

提交完毕后执行，git status将显示有一棵干净的工作树

```shell
git status

On branch main
nothing to commit, working tree clean

```

---

### 使用'git show'检测提交历史

*git-show：* 检查最近一次的提交

*git-show SHA：* 利用每次提交给的SHA查看之前的提交记录

*git show HEAD：* 检查处于main分支头部的提交

---

### 交互式Git暂存

*1、Amend：* 修改提交消息 

```shell
git commit --amend
```

——用上下左右找到位置，x建删除，然后输入新消息。Esc退出输入模式，:wq退出amend



*2、git show HEAD^：* 显示之前的提交记录

```shell
git show HEAD^
```

> 我的shell可能不支持分页，以后在其他终端查看

*3、git add .(剩余的文件)：* 暂存和提交剩余文件

```shell
git add .
```

*4、git reset 文件名：* 取消暂存区文件

```shell
git reset git-config.txt
```

*5、可以使用正则匹配文件名称：* （不举例子了）

*6、进入交互模式：* 

```shell
git add -i//进入交互模式
//交互模式各种功能都有介绍，不过多赘述
```

---

### 优化Git日志输出以获得更好的工作流程

*git log：* 命令显示存储库中的提交列表

```shell
git log
```

> 为了更美观的显示

```shell
git log --oneline
```

在config中将oneline设置为默认

```shell
git config format.pretty oneline//设置为oneline
git config log.abbrevCommit true//使得SHA缩写展示
```

---



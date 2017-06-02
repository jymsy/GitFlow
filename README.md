GitFlow
=======

安装
-----------

[下载git](https://git-scm.com/downloads)

配置
-----------
配置的是你个人的用户名称和电子邮件地址。这两条配置很重要，每次 Git 提交时都会引用这两条信息，说明是谁提交了更新，所以会随更新内容一起被永久纳入历史记录：

```sh
$ git config --global user.name "蒋羽萌"
$ git config --global user.email jiangyumeng@izaodao.org
```

生成SSH密钥

```sh
ssh-keygen -t rsa -C "jiangyumeng@izaodao.org"
```
一路回车

查看SSH密钥
Windows Command Line:
```sh
type %userprofile%\.ssh\id_rsa.pub
```
GNU/Linux/Mac/PowerShell:
```sh
cat ~/.ssh/id_rsa.pub
```
密钥大概长这样

![本地仓库](https://raw.githubusercontent.com/jymsy/GitFlow/zaodao/2.jpg)

将密钥全部复制，包括最后的邮箱，后面会用到.


设置gitlab
-----------
[进入gitlab](http://192.168.1.196:10080)

点击左下角头像进入个人资料

![本地仓库](https://raw.githubusercontent.com/jymsy/GitFlow/zaodao/1.png)

点击左侧个人资料设置

![本地仓库](https://raw.githubusercontent.com/jymsy/GitFlow/zaodao/2.png)

设置姓名和邮箱

![本地仓库](https://raw.githubusercontent.com/jymsy/GitFlow/zaodao/3.png)

点击SSH密钥

![本地仓库](https://raw.githubusercontent.com/jymsy/GitFlow/zaodao/1.jpg)

将之前复制的密钥粘到公钥输入框中，标题随便写，点击增加密钥

添加成功后可以在下面看到添加好的密钥

![本地仓库](https://raw.githubusercontent.com/jymsy/GitFlow/zaodao/3.jpg)

拉取代码
-----------
进入项目的主页，根据箭头所指，选择ssh，然后点击复制按钮

![本地仓库](https://raw.githubusercontent.com/jymsy/GitFlow/zaodao/4.jpg)

通过命令行进入想要存放代码的目录，然后执行:
```sh
git clone ssh://git@192.168.1.196:10022/jymsy/testcpss.git
```

如果觉得通过命令行操作麻烦也可以使用图形界面的工具，比如[SourceTree](https://www.sourcetreeapp.com/)


开发功能
-----------
1. 创建分支

在PMS中找到已经建好的任务

![本地仓库](https://raw.githubusercontent.com/jymsy/GitFlow/zaodao/5.jpg)

在本地的代码目录中，执行创建分支的命令：
```sh
git checkout -b jym-task-1803 origin/develop
```
`jym-task-1803`是新创建的分支名。规则如下：

名字首字母缩写-task/bug-task/bug id

`origin/develop`表示基于远程仓库的develop分支创建，**所有新分支都要基于develop分支建立**。

2. 提交修改

当完成功能的开发之后，首先通过
```sh
git fetch origin
git status
```
获取远程分支的内容更新，例如:
```sh
$ git status
位于分支 jym-task-1803
您的分支落后 'origin/develop' 共 1 个提交，并且可以快进。
  （使用 "git pull" 来更新您的本地分支）
无文件要提交，干净的工作区
```
说明远程分支有更新，需要执行`git rebase`更新本地分支：
```sh
$ git rebase
首先，回退分支以便在上面重放您的工作...
快进 jym-task-1803 至 refs/remotes/origin/develop。
```
再次执行`git status`
```sh
$ git status
位于分支 jym-task-1803
您的分支与上游分支 'origin/develop' 一致。
无文件要提交，干净的工作区
```
说明更新完毕，**有的时候会有冲突，要先解决冲突，再提交**。





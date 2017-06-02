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

在gitlab项目中点击“新分支”

![本地仓库](https://raw.githubusercontent.com/jymsy/GitFlow/zaodao/6.jpg)


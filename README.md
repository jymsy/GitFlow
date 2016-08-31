GitFlow
=======

Description
-----------

![本地仓库](https://raw.githubusercontent.com/jymsy/GitFlow/master/1.png)

其中jymsy / Mango 是我们fork到自己账户下的仓库，sugareps/Mango是远程的主仓库。我们提交的所有代码都
向我们自己账户下的仓库提交，然后再通过提pull request的方式merge到远程主仓库。




详细工作流
-----

当在github上fork之后复制git@github.com:jymsy/Mango.git

![本地仓库](https://raw.githubusercontent.com/jymsy/GitFlow/master/2.png)

本地打开命令行，执行
```sh
$ git clone git@github.com:jymsy/Mango.git
```

克隆完成后已经把代码下载到本地， 执行
```sh
$ git remote -v`
```

可以看到origin已经被添加进来
```sh
➜  Mango/ git:(ibmd_100841) git remote -v
origin    git@github.com:jymsy/Mango.git (fetch)
origin  git@github.com:jymsy/Mango.git (push)

```

我们还需要添加一个名为upstream的远端仓库，每次创建新分支的时候要基于这个远端仓库。这个远端仓库的地址
就是被你fork的那个仓库的地址。
```sh
$ git remote add upstream git@github.com:sugareps/Mango.git
```

添加完成之后再次执行 git remote -v
```sh
➜  Mango/ git:(ibmd_100841) git remote -v
origin    git@github.com:jymsy/Mango.git (fetch)
origin  git@github.com:jymsy/Mango.git (push)
upstream    git@github.com:sugareps/Mango.git (fetch)
upstream    git@github.com:sugareps/Mango.git (push)
```
已经添加上了upstream。


编写代码 提交
-----
比如说我现在要做个UT的task，现在本地创建一个新分支，这个分支要基于upstream。
先执行
```sh
$ git fetch upstream
```
从远端仓库下载新分支与数据，然后创建分支
```sh
$ git checkout -b ibmt_xxx upstream/SC3.6
```
`ibmt_xxx`就是新的分支名，`upstream/SC3.6`表示基于upstream的SC3.6分支（这个分支要存在），创建完成后
执行`git branch`
```sh
$ git branch
  ibmd_100698
* ibmt_xxx

```
可以看到刚刚创建的分支，执行`git status`
```sh
$ git status
位于分支 ibmt_xxx
您的分支与上游分支 'upstream/SC3.6' 一致。
nothing to commit, working tree clean
```
上游分支为`upstream/SC3.6`

修改完代码之后，执行
```sh
$ git add *
$ git commit -m "xxxxxxxx"
$ git push origin HEAD
```
提交代码到自己的分支。然后到github上创建pull request即可。


GitLab GitHub 共存
=======

生成密钥

```sh
$ ssh-keygen -t rsa -C "注册的gitlab邮箱"  //默认设置
$ ssh-keygen -t rsa -C "注册的github邮箱" //设置key  为id_rsa_github
```

创建config

```sh
cd ~/.ssh
touch config

//在config文件下复制一下设置
# gitlab
Host 192.168.1.196
PreferredAuthentications publickey
IdentityFile ~/.ssh/id_rsa
Port 10022

# github
Host github.com
User jymsy
Hostname ssh.github.com
PreferredAuthentications publickey
IdentityFile ~/.ssh/id_rsa_github
Port 443
```

检测

```sh
//测试github
$ ssh -T git@github.com
 
//测试gitlab
$ ssh -T git@192.168.1.196
```

使用

```sh
在对应的github和gitlab上settings里面配置SSH keys （指定的.pub密钥）
```

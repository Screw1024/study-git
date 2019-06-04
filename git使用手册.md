### 账户相关

查看用户名和邮箱地址：

```
$ git config user.name

$ git config user.email
```

修改用户名和邮箱地址：

```
$ git config --global user.name "username"

$ git config --global user.email "email"
```

删除账户名（例如删除账户名为 lisi 的账户名）

~~~ git config --global --unset user.name lisi

git config --global --unset user.name lisi
~~~



### push相关

基本命令

```
   git init //把这个目录变成Git可以管理的仓库
　　git add README.md //文件添加到仓库
　　git add . //不但可以跟单一文件，还可以跟通配符，更可以跟目录。一个点就把当前目录下所有未追踪的文件全部add了，后接文件名需要加上拓展名
　　git commit -m "first commit" //把文件提交到仓库
　　git remote add origin git@github.com:wangjiax9/practice.git //关联远程仓库
　　git push -u origin master //把本地库的所有内容推送到远程库上
```



### 如何解决failed to push some refs to git

出现错误的主要原因是github中的README.md文件不在本地代码目录中

可以通过如下命令进行代码合并【注：pull=fetch+merge]

~~~
git pull --rebase origin master
~~~

同步Readme后再次提交

~~~
git push -u origin master
~~~



### 删除文件和文件夹

在github上只能删除仓库,却无法删除文件夹或文件, 所以只能通过命令来解决

~~~
$ git pull origin master 将远程仓库里面的项目拉下来

$ dir  查看有哪些文件夹

$ git rm -r --cached target  删除target文件夹
$ git commit -m '删除了target'  提交,添加操作说明

$ git push -u origin master 将本次更改更新到github项目上去
~~~


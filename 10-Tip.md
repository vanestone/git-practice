# git-practice
Git  学习笔记
### Git Commands

```bash
git init                    #初始化目录
git status                  #查看工作区和暂存区内容
git add --help              #添加文件到暂存
git commit -m ‘tip’         #提交暂存文件到仓库

git diff --help             #比较文件变更内容
git diff HEAD -- <file>     #查看工作区和版本库里面最新版本的区别

git checkout -- <file>      #还原版本库文件至工作区
git reset HEAD <file>       #撤销暂存区的修改

git rm <file>               #删除文件
```

```bash
#origin 远程库
git remote add origin git@github.com:vanestone/git-practice.git
#将本地分支推送到远程库分支
git push <远程库> <本地分支>:<远程分支>

#如果当前分支只有一个远程分支，那么主机名都可以省略
git push

#查看远程库分支
git branch -r

#如果远程分支被省略，如上则表示将本地分支推送到与之存在追踪关系的远程分支（通常两者同名），如果该远程分支不存在，则会被新建
git push origin master

#如果省略本地分支名，则表示删除指定的远程分支，因为这等同于推送一个空的本地分支到远程分支，等同于 git push origin --delete master
#refs/for 的意义在于我们提交代码到服务器之后是需要经过code review 之后才能进行merge的，而refs/heads 不需要
git push origin :refs/for/master

#如果当前分支与远程分支存在追踪关系，则本地分支和远程分支都可以省略，将当前分支推送到远程库的对应分支
git push origin

#如果当前分支与多个主机存在追踪关系，则可以使用 -u 参数指定一个默认主机，这样后面就可以不加任何参数，一般第一次推送时加上，之后可以省略
git push -u origin master

#不管是否存在对应的远程分支，将本地的所有分支都推送到远程主机
git push --all origin

#强制提交本地分支至远程库对应分支
git push --force origin

#git push 的时候不会推送分支，如果一定要推送标签的话那么可以使用这个命令
git push origin --tags
```


```bash
git log                            #查看git提交日志
git reflog                         #查看git操作日志
git reset --hard HEAD^|commit_id   #回退到 上个版本HEAD^或指定版本Id
```

> *Tip:*
> - `HEAD` 当前版本
> - `HEAD^` 上个版本
> - `HEAD^^` 上上个版本
> - `HEAD~5` 前5个版本a
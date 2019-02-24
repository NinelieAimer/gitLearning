# 学习git心得笔记

git是一个管理仓库工具，支持写日子，恢复以前的数据非常有用。

## git的创建仓库命令

```g
//打开文件夹

cd /e/learning/learngit


//然后就可以在这个文件夹内创建仓库

$ mkdir [repository name]


//让git获取权限

$ git init
```



## git 的一些操作命令

```
$git commit -m "change items"       //每次改变传递的描述

$git log      //获取日志

$git relog   //这个可以获取每次改变版本号，方便恢复
```



```
$ git reset --hard HEAD^    //退回了上一个版本
```

$ git reset --hard [version]     //这里是退后到某个版本，用relog就可以获取

## git 的一些可以查看状态的命令

```
$git log     //查看日志

$git relog      //查看各种修改的版本

$git status    //查看状态，是否出现修改没有添加到仓库

$git diff      //这里可以看到更改以前的不同
```

## git的注意事项

如果每次修改不用git add 添加的话，都会报出没有提交，所以每次修改完成，都要git add一下，然后最后一次提交git commit,这样才可以让暂存区的东西一起提交。

## git撤回修改

```
git checkout -- [file]      //总之，就是让这个文件回到最近一次`git commit`或`git add`时的状态。
git reset HEAD <file>       //这样可以把add以后，但是没有commit的东西，退回修改
```

## git删除文件

```
$rm [file]

$git rm [file]

$ git commit -m "reason"
```

## github本地仓库上传管理

### 首先要在github上创建一个仓库

### 然后在git上运行如下命令

```
$ git remote add origin git@github.com:Nineliebehind/[本地仓库名称].git
```

### 然后把本地内容推送到上面，用以下命令

```
$ git push -u origin [branch name]    //只有第一次要这样，之后可以简化代码
```

### 以后推送只要

```
git push origin master   //这样就可以把最新的东西推上
```

## github从远程关联本地

### 这里将远程的仓库克隆到本地

```
$ git clone git@github.com:michaelliao/[仓库名字].git
```

## github从分支管理

### 创建分支,并且切换分支

```
$git checkout -b [branch name]
```

### 查看分支

```
$git branch
```

### 切换分支

```
git checkout [branch name]
```

### 合并分支

进入某一分支，然后就可以把别的分支合并到这个分支

$git merge [branch name]

### 删除分支

```
git branch -d [branch name]
```

## git的bug分支

git有时候你开发到一半，要暂停去修复bug.你就要保留你现在内容，而且暂存区要是干净的，你可以调用如下命令

```
$ git stash
```

这样就创建了一个快照类似的东西而且还是干净的，当你需要回来工作时候有两种恢复方法

```
git stash apply     //这样slash内容不会删除，你要调用git stash drop删除

//第二种直接删除,连同slash
git stash pop

```

## git 创建标签

```
git tag [tag name]  [commit id]   //版本可写可不写
git show [tag name]  //这样就可以看到这个标签的详细信息
git tag -a [tag name] -m "descripe" [commit id]   //也能提交描述
```

## git推送标签

git不能自动推送标签需要用

```
git push origin [tag name]   //这样才可以推送标签去远程
git push origin --tags      //一次性推送所有标签

```

git 删除标签

```
//首先要删除本地的标签
git tag -d [tag name]   
//然后删除远端的标签
git push origin:refs/tags/[tag name]
```


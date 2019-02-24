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
```


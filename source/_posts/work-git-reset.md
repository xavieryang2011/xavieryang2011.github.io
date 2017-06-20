---
layout: hexo
title: git reset与git reset hard的区别
date: 2017-06-20 17:14:48
tags: 工作
---
今天遇到一个问题，commit后发现一些不需要的内容也提交了，这个时候还没有push到远程服务器怎么办？当然首先想到的就是撤销这次提交，索性用git reset -hard [commitid],执行完，坏了，发现本地的修改也全部回滚了，还好本地做了备份，那应该怎么办呢？果断用git reset [commitid],完整版是git reset 9413d2b,这样只会撤销这次提交，而本地文件还是撤销回去，接下来就是看需要提交哪几个文件再提交就可以了。
commitid怎么找呢，git reflog命令，找到上一个commitid就可以了，和git log的区别自个一试便知。
最近发现git功能真是强大，各种命令确实可以提升工作效率，那么常用的有哪些呢：
git pull --拉取远程数据
git push --推送到远程服务器
git add  --添加要提交的文件
git commit -m ''--提交文件
git branch --查看本地分支
git branch branchname --新建分支branchname
git checkout branchname --切换分支到branchname
git reset --撤销操作
git clone giturl /url --复制远程giturl到本地路径url

暂时就写这么多吧，回头再补充。。。。。。

![](/images/git.png)
---
title: work-git-status
date: 2017-06-27 15:15:39
tags: [work,git]
---
今天项目中用到了git status,相信大家也会经常遇到类似的问题：当在一个分支上做开发时，突然QA抛出一个线上的问题，这时就需要翻出线上分支的代码，可是目前开发的分支又还没有达到提交的状态，怎么办？这个时候就用到了status,说白了就是一个临时存储仓库。能过git stash命令将所有变更暂存起来。
去另一分支修改代码，好，这时候新的问题出现了，如果真是线上bug，又不能在线上分支做提交，这个是时候还得将线上分支的修改代码同步到开发分支master,继续用git status,这个时候就需要注意了，暂存是不区分是那个分支的，也就是说你在A分支下暂存的代码在B分支也是可用的。到这一步，把线上分支的代码也暂存好了，那就切换分支到master开发分支吧，然后就要是怎么恢复暂存的代码了。git stash apply命令默认恢复最近的一个暂存，通过git stash list可能查看所有的暂存列表：

stash@{0}: WIP on 1500: 0fc3c93 1、新增渠道
stash@{1}: WIP on master: 3ecc801 更新版本号等
stash@{2}: On master: Uncommitted changes before Update at 17/5/19 18:58
stash@{3}: WIP on 1300: 0d4813e 创建1300分支
stash@{4}: On master: Uncommitted changes before Update at 17/5/4 21:07
stash@{5}: On master: Uncommitted changes before Update at 17/5/3 16:27
stash@{6}: On master: Uncommitted changes before Update at 17/3/2 12:18
stash@{7}: On master: Uncommitted changes before Update at 17/2/28 12:03

如果想恢复指定暂存，可以用命令git stash apply stash@{1}
好了，相信知道这些个基本用法，可以支撑上一段时日了，哈哈。高级用法还请各位自个研究吧。



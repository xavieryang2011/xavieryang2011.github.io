---
title: git-commond-reset
date: 2017-08-07 20:52:25
tags: git
---
### git reset --head commitid
恢复本地版本到commitid指定版本
### git revert --head commitid
还原指定版本
### 恢复远程服务器到指定版本（danger）
    #### 创建本地分支备份git branch the_branch_backup
    #### git reset--head commitid
    #### git newbranch
    #### git commit/push new branch
    #### 如果是master分支采用上述方法，因为默认master分支是不允许删除的。如果不是master,可以把原分支删除。


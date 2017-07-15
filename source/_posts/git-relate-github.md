---
title: 本地项目托管到github命令行
date: 2017-07-15 18:06:31
tags: git
---
echo "# React-Native-Sample" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/xavieryang2011/React-Native-Sample.git
git push -u origin master

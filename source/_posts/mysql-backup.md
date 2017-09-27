---
title: mysql备份还原
date: 2017-09-27 16:32:33
tags: mysql
---
1.备份数据库
  mysqldump -u 用户名 -p 数据库名 > 导出的文件名 
  mysqldump -u wcnc -p smgp_apps_wcnc > wcnc.sql 
2.将备份文件从服务器拷贝到本地
  scp -r  root@116.196.91.136:/srv/awesome/backup/ templates/
3.还原数据库
  mysql -u root -p awesome < 20170927.sql

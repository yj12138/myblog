+++
date = '2024-11-14T17:29:56+08:00'
draft = false
title= 'mysql 数据库'
+++

1. 安装
   apt-get install mysql-server

   默认 mysql root 没有密码可是直接使用 root 帐户

2. 登录
   mysql -u root -p

   允许用户远程登录
   mysql>GRANT ALL PRIVILEGES ON _._ TO username@"%" IDENTIFIED BY "password";

3. 创建用户
   mysql>create user 'username'@'localhost' identified by 'password';

4. 权限
   mysql>grant select,insert on _._ to 'username'@'localhost' iDENTIFIED by 'password';
   <!-- 所有权限 -->

   mysql>grant ALL PRIVILEGES on _._ to 'username'@'localhost' identified by 'password';
   <!-- 远程 -->

   mysql>grant select,insert on _._ to 'username'@'%' identified by 'password';

5. 查看用户
   select \* from

# 参数链接

    https://blog.csdn.net/qq_42931693/article/details/123819958

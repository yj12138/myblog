+++
date = '2024-11-14T17:29:56+08:00'
draft = false
title= 'ssh 远程登录服务'
+++

1. 安装
   apt-get install openssh-server

2. 查看状态
   systemctl status ssh(sshd)

3. 启动
   systemctl start ssh(sshd)
   /etc/init.d/ssh(sshd) start

4. 关闭
   systemctl stop ssh(sshd)
   /etc/init.d/ssh(sshd) stop

5. 配置
   /etc/ssh/sshd_config

6. 测试连接
   windows ssh 用户名@IP example : ssh yejian@172.30.39.152

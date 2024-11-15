+++
date = '2024-11-14T17:29:56+08:00'
draft = false
title= 'ftp 文件服务搭建'
+++

1. 安装
   apt-get install vsftpd

2. 启动
   systemctl start vsftpd
   systemctl enable vsftpd 开机启动

3. 查看状态
   netstat -antup | grep ftp

4. 配置
   /etc/vsftpd.conf
   配置参数
   anonymous_enable=NO
   local_enable=YES
   chroot_local_user=YES
   chroot_list_enable=YES
   chroot_list_file=/etc/vsftpd/chroot_list
   listen=YES
   write_enable=YES

   listen_ipv6=YES ipv6 监听 可以注释

5. 重启服务
   systemctl restart vsftpd

6. 设置权限
   vim /etc/sudoers5. 重启服务
   systemctl restart vsftpd

# 参数链接

    https://blog.csdn.net/huyongfu2004/article/details/122710325

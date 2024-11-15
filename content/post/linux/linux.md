+++
date = '2024-11-14T17:29:56+08:00'
draft = false
title= '常用命令'
+++

# 创建用户

    useradd -m username
    -m 创建用户目录

# 设置密码

    passwd username

# 服务

<!-- 查看服务 -->

service --status-all

# 设置时区

    tzselect
    ->Asia
    ->China
    ->BeiJing
    ->Yes
    sudo cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
    date -R

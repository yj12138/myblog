+++
date = '2024-11-14T17:29:56+08:00'
draft = false
title= '安装 kafka'
+++

## 准备工作

1. 安装 jdk
   apt-get install openjdk-8-jdk-headless

2. 下载 zooKeeper
   url <http://archive.apache.org/dist/zookeeper/>
   选择 3.4.9

3. 配置 zooKeeper
   tar -zxvf zookeeper-3.4.10.tar.gz
   cp zookeeper-3.4.10 /usr/local/zookeeper -r
   cd /usr/local/zookeeper
   添加环境变量
   export ZOOKEEPER=/usr/local/zookeeper
   export PATH=$PATH:$ZOOKEEPER/bin
   source /etc/profile

4. zookeeper 启动
   zkServer.sh start
   zkServer.sh status
   zkServer.sh stop

## 下载 kafka

1. 安装
   wget http://mirrors.shuosc.org/apache/kafka/1.0.0/kafka_2.11-1.0.0.tgz
   tar -zxvf kafka_2.11-1.0.0.tgz
   vim config/server.properties
2. 启动
   bin/kafka-server-start.sh config/server.properties
   <!-- 后台启动 -->
   kafka-server-start.sh -daemon ../config/server.properties

# 参考链接

<https://blog.csdn.net/weixin_44088559/article/details/108469030>

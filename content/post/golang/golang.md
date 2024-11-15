+++
date = '2024-11-14T17:29:56+08:00'
draft = false
title= '编译golang源码'
+++

# linux golang 源码编译

1. 下载代码
   git clone https://github.com/golang/go.git

2. 先编译 go1.4
   <!-- 在当前用户目录下 -->

   cp -R go/ go1.4
   git checkout release-branch.go1.4
   cd src
   ./all.bash
   <!-- 设置GOROOT -->

   export GOROOT=~/go1.4

3. 编译 go1.16.15
   git checkout release-branch.go1.16
   cd src
   ./all.bash
   <!-- 重新设置 -->

   vim ~/.bashrc
   PATH=$PATH:~/go.15.16/bin
   GOROOT=~/go.15.16

4. 配置
   go env -w GO111MODULE=auto
   go env -w GOPATH=~/go
   go env -w GOPROXY=https://goproxy.cn,direct

# 参考链接

<https://www.freesion.com/article/17261172649/>

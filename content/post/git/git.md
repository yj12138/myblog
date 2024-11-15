+++
date = '2024-11-14T17:29:56+08:00'
draft = false
title= 'git常用命令'
+++

## 配置

### 查看设置

```shell
git config --list
```

### 设置用户邮箱

```shell
git config --global user.name "xxxx"
git config --global user.email "xxxx"
```

### 保存用户凭证

```shell
git config credential.helper store
```

## 创建

```shell
#当前目录初始化仓库
git init
```

```shell
#克隆仓库
git clone url
```

## 管理

<!-- git add -->

```shell
git add
```

```shell
git commit
```

```shell
git status
```

```shell
git log
```

```shell
git tag
```

```shell
git diff
```

```shell
git branch
```

## 远程

```shell
#设置远程链接
git remote add origin url
```

```shell
# 拉取远程分支master并合并到当前分支
git pull origin master
```

## 合并

## 推送

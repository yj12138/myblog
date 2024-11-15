+++
date = '2024-11-14T17:29:56+08:00'
draft = false
title= 'miniconda python 环境、包管理工具'
+++

## 基本信息

    conda info

![icon conda_info](/images/conda_info.png)

### 查看环境

    conda info --envs

## 查看下载源

    conda config --show channels

## 配置源

    conda config --set show_channel_urls yes //生成 .condarc 的文件
    copy 下面的内容

```
channels:
  - defaults
show_channel_urls: true
default_channels:
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/r
custom_channels:
  conda-forge: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  msys2: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  bioconda: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  menpo: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  pytorch: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  simpleitk: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
ssl_verify: false
```

## 创建环境

    conda create
    -n 名称
    -p 路径
    -clone 克隆一个指定的环境
    python=3.8.5 指定python版本

### eamples:

    conda create -n test sqlite //containing sqlite package
    conda create -n test --clone path/to/env

## 激活环境

    conda activate test

## 删除环境

    conda remove -n test --all

## 更新

    conda update -n base -c defaults conda

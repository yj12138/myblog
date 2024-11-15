+++
date = '2024-11-14T17:29:56+08:00'
draft = false
title= '鸿蒙调用golang代码'
+++

## 踩坑记录

HarmanyOS 调用 Golang 导出的 so

- 方案 1:直接生成 linux 平台 so(失败)
- 方案 2:生成 android 平台 so(成功)

## 方案 1

结论: 鸿蒙 ndk 加载链接 so 会出现 TLS(线程内部存储) 重定位错误

## 方案 2

用鸿蒙的 clang 编译器直接是无法生成 android 平台的 so,要修改 go 源码(如下)

1. 下载安装 go1.22.8
2. src/runtime/cgo/cgo.go

```golang
#cgo android LDFLAGS: -llog
改为
#cgo android LDFLAGS: -lhilog_ndk.z.so
```

3. src/cgo/gcc_android.c

```golang

#include <android/log.h>
改为
#include <hilog/log.h>

android_log_vprint(ANDROID_LOG_FATAL, "runtime/cgo", format, ap);
改为
OH_LOG_FATAL(LOG_APP, format, ap);
```

4. /src/net/cgo_resold.go

```golang

```

5. 生成脚本

```bash
@echo off
set NDK_PATH=D:\OpenHarmonySDK\12\native

set SO_NAME=libopenimsdk
set OUT_PATH=openharmony\

set CGO_ENABLED=1

set NM=%NDK_PATH%\llvm\bin\llvm-nm
set AR=%NDK_PATH%\llvm\bin\llvm-ar
set LD=%NDK_PATH%\llvm\bin\ld.lld
set BASE_FLAGS=--sysroot=%NDK_PATH%\sysroot -fdata-sections -ffunction-sections -funwind-tables -fstack-protector-strong -no-canonical-prefixes -fno-addrsig -Wformat -Werror=format-security  -D__MUSL__ -fPIC -MD -MT -MF

REM arm64-v8a
set GOOS=android
set GOARCH=arm64
set CXXFLAGS=--target=aarch64-linux-ohos %BASE_FLAGS%
set CFLAGS=--target=aarch64-linux-ohos %BASE_FLAGS%
set CC=%NDK_PATH%\llvm\bin\clang %CFLAGS% %BASE_FLAGS%
set CXX=%NDK_PATH%\llvm\bin\clang++ %CFLAGS% %BASE_FLAGS%

go build -buildmode=c-shared  -trimpath -ldflags="-s -w" -o %OUT_PATH%arm64-v8a\%SO_NAME%.so ./

REM x86_64
set GOOS=android
set GOARCH=amd64
set CXXFLAGS=--target=x86_64-linux-ohos %BASE_FLAGS%
set CFLAGS=--target=x86_64-linux-ohos %BASE_FLAGS%
set CC=%NDK_PATH%\llvm\bin\clang %CFLAGS% %BASE_FLAGS%
set CXX=%NDK_PATH%\llvm\bin\clang++ %CFLAGS% %BASE_FLAGS%
go build  -buildmode=c-shared  -trimpath -ldflags="-s -w" -o %OUT_PATH%x86_64\%SO_NAME%.so ./
```

结论：可以直接链接并调用 so 的函数,具体调用过程省略

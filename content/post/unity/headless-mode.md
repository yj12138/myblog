+++
date = '2024-11-14T17:29:56+08:00'
draft = false
title= 'Unity Headless Mode 命令行离屏渲染模型'
+++

## -batchmode：

这个参数将 Unity 设置为批处理模式。在批处理模式下，Unity 不会显示图形用户界面，这对于无人值守的构建和自动化任务很有用。
当你使用 -batchmode 时，Unity 将在不启动图形用户界面的情况下执行所需的任务，例如构建、导出场景等。
示例命令：YourApp.exe -batchmode -executeMethod YourScript.YourMethod -quit
-executeMethod 参数用于在批处理模式下执行指定的 C# 方法。

## -nographics：

这个参数禁用 Unity 的图形渲染系统。在使用 -nographics 时，Unity 不会尝试初始化和运行图形渲染管道，因此不会创建图形窗口。
这对于那些只关心命令行操作而不需要图形界面的场景很有用，比如离屏渲染、自动化测试等。
示例命令：YourApp.exe -batchmode -nographics -executeMethod YourScript.YourMethod -quit

## -executeMethod 执行选定方法

## -logFile path 日志路径

## -projectPath 项目打包路径

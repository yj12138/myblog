+++
date = '2024-11-14T17:29:56+08:00'
draft = false
title= 'VSCode 导出所有插件'
+++

```bash
@echo off
for /F %%i in ('code --list-extensions') do @echo code --install-extension %%i >> install.bat
echo succeed
pause
```

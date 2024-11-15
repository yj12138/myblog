---
title: 设置
categories: VSCode
tags:
---

```json
{
    "security.workspace.trust.enabled": false, //信任文件夹

    "editor.fontSize": 18, //字体18
    "editor.renderControlCharacters": true, //不显示右侧缩略图
    "editor.cursorStyle": "line", //
    "editor.lineNumbers": "on", //显示行号
    "editor.wordWrap": "off", //
    "editor.wordSeparators": "/\\()\"':,.;<>~!@#$%^&*|+=[]{}`?-",
    "editor.detectIndentation":false,
    "editor.tabSize": 4, //tab 两个字符

    "diffEditor.ignoreTrimWhitespace": false,

    "workbench.statusBar.visible": true, //显示状态栏
    "workbench.editor.enablePreview": false, //显示主题
    "workbench.colorCustomizations": {
      "tab.activeBackground": "#037780", //激活的文档背景色
      "tab.activeForeground": "#ffffff", //激活的文档前景色
    },
    //vim
    "vim.foldfix": true,
    // extensions 配置
    "git.path": "D:\\Program Files\\Git\\bin",
    "[go]": {
        "editor.insertSpaces": true,
        "editor.formatOnSave": false,
        "editor.codeActionsOnSave": {
            "source.organizeImports": false,
        },
        "editor.suggest.snippetsPreventQuickSuggestions": false
    },
    "go.toolsManagement.autoUpdate": true,
    //cmake 
    "cmake.configureOnOpen": true,
    "cmake.configureOnEdit": false,
    // 控制台显示 中文
    "terminal.integrated.profiles.windows": {
      "PowerShell": {
        "source": "PowerShell",
        "icon": "terminal-powershell"
      },
      "Command Prompt": {
        "path": [
          "${env:windir}\\System32\\cmd.exe"
        ],
        "args": ["/K chcp 65001 >nul"],
        "icon": "terminal-cmd"
      },
      "Git Bash": {
        "source": "Git Bash"
      }
    },
    "terminal.integrated.defaultProfile.windows": "Command Prompt",
    "go.formatTool": "goformat",
    "go.languageServerExperimentalFeatures": {
      "diagnostics": false
    },
    "workbench.startupEditor": "none",
    "editor.links": false,
    // "go.buildOnSave": "off",
    // "go.lintOnSave": "off",
    // "go.vetOnSave": "off",
    "editor.semanticHighlighting.enabled": true,
    "Lua.color.mode": "Grammar",
    "Lua.completion.requireSeparator": "/",
    "Lua.telemetry.enable": false,
    // "omnisharp.useModernNet": false,
    "update.mode": "manual",
    "extensions.autoUpdate": false,
    "extensions.autoCheckUpdates": false,
    "workbench.colorTheme": "Monokai",
    "C_Cpp.workspaceSymbols": "All",
    "C_Cpp.addNodeAddonIncludePaths": true,
    "C_Cpp.default.compilerPath": "${default}",
    "editor.unicodeHighlight.invisibleCharacters": false,
    "omnisharp.loggingLevel": "error",
    "git.enabled": false,
    "remote.SSH.remotePlatform": {
        "192.168.78.3": "linux"
    },
    "window.commandCenter": true,
    "editor.minimap.enabled": false,
    "dart.debugExternalPackageLibraries": false,
    "dart.debugSdkLibraries": false,
}
```
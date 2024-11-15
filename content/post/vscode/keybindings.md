+++
date = '2024-11-14T17:29:56+08:00'
draft = false
title= 'VSCode按键绑定'
+++

```json
[
  {
    "key": "ctrl+9",
    "command": "-workbench.action.lastEditorInGroup"
  },
  {
    "key": "ctrl+9",
    "command": "workbench.action.focusFirstEditorGroup"
  },
  {
    "key": "ctrl+1",
    "command": "-workbench.action.focusFirstEditorGroup"
  },
  {
    "key": "ctrl+0",
    "command": "workbench.action.focusSecondEditorGroup"
  },
  {
    "key": "ctrl+2",
    "command": "-workbench.action.focusSecondEditorGroup"
  },
  {
    "key": "ctrl+f",
    "command": "-extension.vim_ctrl+f",
    "when": "editorTextFocus && vim.active && vim.use<C-f> && !inDebugRepl && vim.mode != 'Insert'"
  },
  {
    "key": "ctrl+w",
    "command": "-extension.vim_ctrl+w",
    "when": "editorTextFocus && vim.active && vim.use<C-w> && !inDebugRepl"
  },
  {
    "key": "ctrl+b",
    "command": "-extension.vim_ctrl+b",
    "when": "editorTextFocus && vim.active && vim.use<C-b> && !inDebugRepl && vim.mode != 'Insert'"
  },
  {
    "key": "ctrl+shift+c",
    "command": "-workbench.action.terminal.openNativeConsole",
    "when": "!terminalFocus"
  },
  {
    "key": "ctrl+shift+c",
    "command": "-workbench.action.terminal.copySelection",
    "when": "terminalFocus && terminalProcessSupported && terminalTextSelected && terminalTextSelected"
  },
  {
    "key": "ctrl+shift+c",
    "command": "workbench.action.terminal.toggleTerminal",
    "when": "terminal.active"
  },
  {
    "key": "ctrl+oem_3",
    "command": "-workbench.action.terminal.toggleTerminal",
    "when": "terminal.active"
  },
  {
    "key": "ctrl+k",
    "command": "workbench.action.terminal.clear",
    "when": "terminalFocus"
  },
  {
    "key": "ctrl+a",
    "command": "-extension.vim_ctrl+a",
    "when": "editorTextFocus && vim.active && vim.use<C-a> && !inDebugRepl"
  },
  {
    "key": "ctrl+c",
    "command": "-extension.vim_ctrl+c",
    "when": "editorTextFocus && vim.active && vim.overrideCtrlC && vim.use<C-c> && !inDebugRepl"
  },
  {
    "key": "ctrl+x",
    "command": "-extension.vim_ctrl+x",
    "when": "editorTextFocus && vim.active && vim.use<C-x> && !inDebugRepl"
  },
  {
    "key": "ctrl+v",
    "command": "-editor.action.clipboardPasteAction"
  }
]
```

# vscode shortcut for step by step

## 打开 vscode

#### 1. 按(Command + Shift + P)组合键(Mac 系统下)，或者(Control + Shift + P)组合键(其他系统下),

#### 2. 输入 Keyboard Shortcuts, 然后选择

> Preferrences: Open Keyboard Shortcuts(JSON)

#### 3. 修改 keybindings.json,类似下面

```json
// 将键绑定放在此文件中以覆盖默认值
[
  {
    "key": "shift+enter",
    "command": "workbench.action.terminal.runSelectedText"
  }
]
```

[尝鲜](03-start.md) | [返回](README.md)

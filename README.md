# Auto.js-VSCodeExt README

桌面编辑器 Visual Studio Code 的插件。可以让 Visual Studio Code 支持[Auto.js](https://github.com/hyb1996/NoRootScriptDroid)开发。

## Install

在 VS Code 中菜单"查看"->"扩展"->输入"Auto.js"或"hyb1996"搜索，即可看到"Auto.js-VSCodeExt"插件，安装即可。插件的更新也可以在这里更新。

## Features

目前功能比较基础，仅支持：

- 在 VS Code 的开发者工具实时显示 Auto.js 的日志与输出
- 在 VS Code 命令中增加 Run, Stop, Rerun, Stop all 等选项。可以在手机与电脑连接后把 Sublime 编辑器中的脚本推送到 AutoJs 中执行，或者停止 AutoJs 中运行的脚本。

## Usage

### Step 1

按 `Ctrl+Shift+P` 或点击"查看"->"命令面板"可调出命令面板，输入 `Auto.js` 可以看到几个命令，移动光标到命令`Auto.js: Start Server`，按回车键执行该命令。

此时 VS Code 会在右上角显示"Auto.js server running"，即开启服务成功。

### Step 2

将手机连接到电脑启用的 Wifi 或者同一局域网中。通过命令行 ipconfig(或者其他操作系统的相同功能命令)查看电脑的 IP 地址。在[Auto.js](https://github.com/hyb1996/Auto.js)的侧拉菜单中启用调试服务，并输入 IP 地址，等待连接成功。

### Step 3

之后就可以在电脑上编辑 JavaScript 文件并通过命令`Run`或者按键`F5`在手机上运行了。

## Commands

按 `Ctrl+Shift+P` 或点击"查看"->"命令面板"可调出命令面板，输入 `Auto.js` 可以看到几个命令：

- Start Server: 启动插件服务。之后在确保手机和电脑在同一区域网的情况下，在 Auto.js 的侧拉菜单中使用连接电脑功能连接。
- Stop Server: 停止插件服务。
- Run 运行当前编辑器的脚本。如果有多个设备连接，则在所有设备运行。
- Rerun 停止当前文件对应的脚本并重新运行。如果有多个设备连接，则在所有设备重新运行。
- Stop 停止当前文件对应的脚本。如果有多个设备连接，则在所有设备停止。
- StopAll 停止所有正在运行的脚本。如果有多个设备连接，则在所有设备运行所有脚本。
- Save 保存当前文件到手机的脚本默认目录（文件名会加上前缀 remote)。如果有多个设备连接，则在所有设备保存。
- RunOnDevice: 弹出设备菜单并在指定设备运行脚本。
- SaveToDevice: 弹出设备菜单并在指定设备保存脚本。
- New Project（新建项目）：选择一个空文件夹（或者在文件管理器中新建一个空文件夹），将会自动创建一个项目
- Run Project（运行项目）：运行一个项目，需要 Auto.js 4.0.4Alpha5 以上支持
- Save Project（保存项目）：保存一个项目，需要 Auto.js 4.0.4Alpha5 以上支持

以上命令一些有对应的快捷键，参照命令后面的说明即可。

## Log

要显示来自 Auto.js 的日志，打开 VS Code 上面菜单的"帮助"->"切换开发人员工具"->"Console"即可。

## config

```js
// autoJs.conf.js
module.exports = {
  scriptFile: './dist/main.js',
};
```

## Self Release Notes

### 0.0.2-beta.1

添加常用功能到左上与编辑的右键菜单，提高开发效率。

注：仅在 JavaScript 格式的文件夹下会展示 run current file，typescript 格式下只会展示 run，（运行整个项目编译之后的结果，前提是项目根目录下存在 `autoJs.conf.js` 并且指定了 `scriptFile`，具体可以参考 [config](##config)）。右键菜单添加了比如 start server 之类的，具体可以自行摸索。

## Release Notes

### 0.0.1

首次发布。包含以下特性：

- 启动，停止服务
- 显示 Auto.js 的日志
- 运行，停止，重新运行脚本
- 多设备连接支持，允许在运行时选择要运行的设备

### 0.0.2

增加以下特性：

- 脚本保存到设备

### 0.2.0

增加以下特性：

- New Project（新建项目）：选择一个空文件夹（或者在文件管理器中新建一个空文件夹），将会自动创建一个项目
- Run Project（运行项目）：运行一个项目，需要 Auto.js 4.0.4Alpha5 以上支持
- Save Project（保存项目）：保存一个项目，需要 Auto.js 4.0.4Alpha5 以上支持

---

### For more information

- [Github repo](https://github.com/hyb1996/Auto.js-VSCode-Extension)

**Enjoy!**

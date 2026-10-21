# VBCC Mac

VBCC 的 Mac 配套应用：接收已配对 iPhone 发来的文字、快捷键和远程触控板操作，并把开发工具的 Hooks 消息转发到已连接的 iPhone。

[VBCC 官网](https://imyiangyang.top/app/vbcc/) · [下载 vbcc-ios（App Store）](https://apps.apple.com/app/id6772499540)

本仓库用于公开分发安装包、版本记录和使用说明。应用源码保存在独立的私有仓库中。

## 系统要求

- macOS 13.0 或更新版本。
- Universal 安装包，包含 Apple Silicon（arm64）和 Intel（x86_64）架构。
- 兼容的 VBCC iPhone 客户端与可互通的局域网。

## 下载与安装

- [下载最新版本](https://github.com/imyiangyang/vbcc-mac-release/releases/latest)
- [下载 v2.0 安装包](https://github.com/imyiangyang/vbcc-mac-release/releases/download/v2.0/vbcc-mac-v2.0.dmg)
- [更新记录](CHANGELOG.md) · [功能与使用说明](FEATURES.md)

1. 下载 DMG，打开后将 `vbcc-mac.app` 拖入「应用程序」。
2. 启动 VBCC Mac，在「系统设置 → 隐私与安全性 → 辅助功能」中授权应用。
3. 让 Mac 和安装了兼容 VBCC 客户端的 iPhone 处于可互通的局域网，并允许系统提示的本地网络访问。
4. 在 iPhone 上发现 Mac 并发起配对，在有效时间内选出 Mac 显示的配对数字。
5. 配对后即可使用文字输入、快捷键和远程触控板；具体入口取决于 iPhone 客户端版本。

应用使用 Developer ID 签名并通过 Apple 公证。Release 提供 SHA-256 校验文件，可在终端核对：

```sh
shasum -a 256 vbcc-mac-v2.0.dmg
```

## 主要功能

- 远程触控板：指针移动、左/右键、双击、左键拖拽、双轴滚动与惯性滚动。
- 文字与键盘：向当前焦点输入框写入文字，支持基本按键、修饰键组合和向前删除。
- 文本润色：可选使用本地 Ollama 或豆包服务，自定义模型、提示词和超时时间。
- Hooks 通知：支持 Claude Code、Codex、Cursor，将相应事件转发至已连接的 iPhone。
- 设备管理：数字配对、已配对设备列表、单台或全部吊销。
- 历史与日志：查看接收的文字、Hooks 消息和运行日志。
- 多语言：简体中文、繁体中文、英语、日语、韩语、法语、德语、西班牙语。

## 使用提示

远程输入需要辅助功能权限。远程触控板需要 iPhone 客户端支持对应功能；仅升级 Mac 应用不会为旧版客户端增加操作入口。

文本润色默认关闭。启用后，待润色文本会发送到你配置的模型服务；使用豆包或远程 Ollama 地址时，请自行确认服务地址与数据处理方式。

安装包和二进制应用的提供不构成源码开源授权。

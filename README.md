# 妙笔 MiaoBi

> A local-first, block-based note app for macOS.

![Release](https://img.shields.io/github/v/release/LingoJack/MiaoBi)
![Platform](https://img.shields.io/badge/platform-macOS%20arm64-black)

[下载最新版](https://github.com/LingoJack/MiaoBi/releases/latest) · [全部版本](https://github.com/LingoJack/MiaoBi/releases) · [问题反馈](https://github.com/LingoJack/MiaoBi/issues)

## 它是什么

妙笔是一款面向 macOS 的离线优先本地笔记应用。它围绕块编辑器组织内容，每篇文档保存为单个自足的文件，所有数据都留在你自己的电脑上：没有账号，没有云端，也不依赖任何在线服务。

编辑器采用块式模型，配合分段渲染引擎，在大文档下依然保持流畅。文档以文件夹为单位组织，文件夹就是真实的目录，可以直接在访达里整理；拷走一个文件，就完成了这篇文档的完整备份与迁移。

如果你使用 AI 工具，妙笔也提供了本机的 MCP 服务器和命令行工具，让外部 AI 客户端能够直接读写你的笔记，整个过程仍发生在本机。

## 特性

### 编辑器

- 块式编辑器，基于 TipTap / ProseMirror
- 分段渲染引擎，大文档滚动与编辑保持流畅
- 支持表格、代码块语法高亮、数学公式、PDF、待办列表、图片与链接预览等块类型
- 折叠面板，便于整理长文档结构

### 画板

- 内置 jgraph 流程图画板
- 内置 Excalidraw 兼容画板
- 支持 Mermaid 语法导入，自动转换为画板内容

### 存储与安全

- 每篇文档是单个 `.jnote` 文件：一个自足的 ZIP 容器，包含正文、附件与元信息
- 拷走单个文件即可完整迁移或备份
- 文件夹即真实目录，可在访达中直接整理
- 保存前自动快照，每份文档最多保留 30 份轮转快照
- 回收站：文档与文件夹删除后可还原
- 自动监听外部文件改动：同步盘或手动编辑的改动会被收编，发生冲突时给出提示

### 窗口与系统集成

- 独立文档窗口、终端窗口、画板窗口、预览窗口
- 命令面板与链接预览多标签
- `Cmd+Tab` 窗口切换器浮层与全局快捷键
- 可自定义应用图标（内置多套）
- 中文界面

## 下载与安装

1. 从 [Releases 页面](https://github.com/LingoJack/MiaoBi/releases)下载最新安装包，或使用最新版直链：
   `https://github.com/LingoJack/MiaoBi/releases/latest/download/MiaoBi-1.2.0-arm64.dmg`
2. 打开 DMG，将妙笔拖入「应用程序」文件夹。

<!-- TODO: 补充安装与首启截图 -->

说明：安装包已通过 Apple Developer ID 签名并经 Apple 公证，macOS 会正常放行，无需手动绕过安全提示。

## 系统要求

- macOS（Apple Silicon，arm64 架构）
- Windows（x64）
- 当前版本：1.2.0

## 数据与隐私

数据存储位置：

- 文档工作区默认位于 `~/Documents/jstudio/`
- 索引与回收站位于 `~/.jdata/studio/`

隐私声明：妙笔不采集任何遥测数据；联网仅发生在你主动触发的功能中（例如抓取链接元数据）。其余时间应用完全离线运行。

## 内置 CLI 与 MCP

**命令行工具**：随应用附带 `j` 命令行工具，例如 `j note` 用于文档读写，`j mcp` 用于 MCP 相关操作。

**MCP 服务器**：应用内置 MCP 服务器，监听本机 `127.0.0.1`（Streamable HTTP），使用 token 鉴权，配置文件位于 `~/.jdata/studio/mcp.json`。外部 AI 客户端可通过它直连读写笔记，提供 20 多个工具，包括读取块、写入块、搜索、画板导出等。

应用内还提供内置 PTY 终端，以及由本地 agent 引擎驱动的对话侧栏。

## 问题反馈

使用中遇到问题或有功能建议，请到 [GitHub Issues](https://github.com/LingoJack/MiaoBi/issues) 提交。为便于定位，建议附上：

- macOS 系统版本
- 复现步骤与预期结果
- 相关报错信息（如有）

## 许可

版权归作者所有，本仓库仅分发二进制安装包。

<!-- TODO: 确认并补充正式许可条款 -->

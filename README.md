<p align="center">
  <img src="./assets/logo.png" width="112" alt="WjnCode" />
</p>

<h1 align="center">WjnCode</h1>

<p align="center">为 Claude Code / Codex CLI 打造的 Windows 桌面工作台</p>

<p align="center">
  <a href="https://gitee.com/wang-jining/wjncode/releases"><strong>下载最新版本</strong></a>
  ·
  <a href="https://gitee.com/wang-jining/wjncode/issues">问题反馈</a>
</p>

---

WjnCode 是一个基于 **Tauri 2 + Rust + React 19** 的 AI 编程桌面应用。它把 Claude Code 与 Codex CLI 装进一个原生窗口里：多项目、多会话、流式对话、工具审批、Git 源代码管理、文件对比、PowerShell 终端和 npm 脚本控制台都在同一个界面里完成。

> **本仓库仅用于产品介绍与安装包发布，不包含源代码。** WjnCode 目前为闭源软件，新版本会发布在 [Releases](https://gitee.com/wang-jining/wjncode/releases)。

## 界面预览

**对话、工具调用与用量统计**

![WjnCode 对话界面](assets/chat.png)

**Git 源代码管理与左右对比**

![WjnCode 源代码管理](assets/source-control.png)

**内置 PowerShell 终端**

![WjnCode 终端](assets/terminal.png)

## 下载

> 当前最新版本：**V1.1.6** · [查看发行说明](https://gitee.com/wang-jining/wjncode/releases/tag/v1.1.6)

| 系统                | 下载                                                    | 说明               |
| ------------------- | ------------------------------------------------------- | ------------------ |
| Windows 10 / 11 x64 | [前往 Releases 下载最新版](https://gitee.com/wang-jining/wjncode/releases) | 绿色单文件，无需安装 |

- 下载后把 `wjn-code.exe` 放到**有写权限的目录**，例如 `D:\Apps\WjnCode\`。不要放进 `C:\Program Files`，否则后续覆盖更新时需要管理员权限。
- 首次运行若出现 Windows SmartScreen 提示，点「更多信息」→「仍要运行」。应用暂未购买代码签名证书。
- 每个版本的 SHA256 会写在对应 Release 的说明里，下载后可自行校验。

## 功能亮点

- **双后端**：每个会话可以选择 Claude Code 或 Codex CLI，模型、权限和斜杠命令互不干扰。
- **多项目与会话**：把本地目录添加为项目，会话按项目归档；支持置顶、重命名、归档和最近会话。
- **流式对话**：实时输出、Markdown 渲染、代码高亮、思考过程、工具调用与结果展示。
- **工具审批**：Claude / Codex 的工具调用会在应用内弹出审批卡片，可选择本次允许、始终允许或拒绝。
- **Git 源代码管理**：查看暂存与未暂存改动、提交、拉取、推送、浏览提交历史，并在中栏左右对比完整 diff。
- **内置终端**：多标签 PowerShell，支持 PTY、方向键、Tab 补全，以及 `vim`、`ssh` 等交互程序。
- **脚本控制台**：一键运行 `package.json` 里的 npm 脚本，保留颜色与进度条，支持多个脚本同时运行。
- **供应商管理**：直连 Anthropic / OpenAI 兼容 API，维护多套配置并随时切换，也可以从 CC Switch 导入。
- **环境检测**：检测并一键安装 Node.js、Claude Code、Codex CLI，自动检查 API 与登录配置。
- **用量统计**：按天统计 token 用量、缓存命中与费用，会话内显示上下文占用。
- **本地优先**：项目、会话和 API 配置都保存在本机；不收集遥测，不经过第三方中转。

## 快速开始

1. 从 [Releases](https://gitee.com/wang-jining/wjncode/releases) 下载最新的 `wjn-code.exe`。
2. 双击运行。首次打开时，顶部会提示环境尚未就绪。
3. 进入 **设置 → 运行环境**，按提示安装 Node.js、Claude Code / Codex CLI。本机已经安装过的话会自动识别。
4. 进入 **设置 → 供应商**，添加 API 地址、API Key 和模型；如果 CLI 已登录官方账号，也可以直接使用。
5. 新建会话，或点侧栏的「+」把本地项目目录添加进来，开始对话。

> 应用会自动检测 `claude`、`codex`、`git`、`npm` 的常见安装位置；安装在非标准路径时，可以通过环境变量覆盖。

## 系统要求

- Windows 10 1809+ / Windows 11，x64
- Microsoft Edge WebView2 Runtime（Windows 11 与已安装新版 Edge 的 Windows 10 通常已内置；缺失时请安装 [Evergreen Runtime](https://developer.microsoft.com/microsoft-edge/webview2/)）
- 建议 8 GB 内存以上
- 使用 Claude Code / Codex 需要可用的 API Key，或对应账号的登录凭据

## 数据与隐私

- 项目、会话索引和供应商配置保存在本机 `%APPDATA%\com.wjnstudio.wjncode\`。
- Claude Code / Codex 的会话记录分别由两个 CLI 写入 `~/.claude` 与 `~/.codex`。
- WjnCode 不收集遥测，不上传代码或对话；请求由本机 CLI 直接发往你配置的服务商。
- 修改 Claude / Codex 的配置文件前，会先备份为 `*.wjncode.bak`。

## 版本与更新

- 每个版本都会在 [Releases](https://gitee.com/wang-jining/wjncode/releases) 中列出更新内容、文件大小和 SHA256。
- 应用内自动更新功能正在开发中。在此之前，请手动下载新版本，**完全退出 WjnCode 后**覆盖旧 exe；项目、会话和配置都保存在本机数据目录，不受替换 exe 影响。
- 更新前建议备份 `%APPDATA%\com.wjnstudio.wjncode\`。

## 常见问题

**打不开，提示缺少 WebView2？**
安装 Microsoft Edge WebView2 Evergreen Runtime 后重试。

**SmartScreen 提示「Windows 已保护你的电脑」？**
应用未签名，属于正常提示。点「更多信息」→「仍要运行」。

**杀毒软件报毒？**
单文件 exe 偶尔会被误报。请只从本仓库 Releases 下载，并用 Release 说明里的 SHA256 校验；必要时把程序目录加入信任。

**数据在哪里？如何备份？**
`%APPDATA%\com.wjnstudio.wjncode\`，复制整个目录即可备份。

**如何卸载？**
关闭 WjnCode，删除 exe；如需彻底清理，再删除上面的数据目录。

**支持 macOS / Linux 吗？**
目前只发布 Windows x64 版本。

**源代码会开源吗？**
本仓库只用于产品介绍与安装包发布，源代码暂不开源。

## 反馈

- 提交 [Issue](https://gitee.com/wang-jining/wjncode/issues) 时，请附上 Windows 版本、WjnCode 版本和复现步骤。
- 请勿在 Issue 中粘贴 API Key、私人代码或会话内容。

## 版权

Copyright © 2026 WjnStudio. All rights reserved.

WjnCode 为闭源软件。本仓库仅用于产品介绍与安装包发布；未经书面许可，不得修改、反向工程、重新打包或商业分发本软件及图标、截图等素材。下载并用于个人或内部工作用途不受限制。
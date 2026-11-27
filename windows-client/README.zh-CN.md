# DNS-DATA Windows 用户端

**独立 Windows 图形客户端** · Windows 10/11（64 位）· **v0.1.27** · 2026 年 11 月 27 日更新

[English](README.md) · **[DNS-DATA 总发布页面](../RELEASES.zh-CN.md)** · [官网 Windows 下载页](https://dns-data.com/zh/download/) · [GitHub Releases 总览](https://github.com/DNSDATA/dns-data-mcp/releases)

这是 DNS-DATA 专门面向 **Windows 用户端**的独立图形程序，用于将用户授权的 Windows 电脑连接至 DNS-DATA Remote MCP 服务。不需要通过命令行安装 npm 启动器。它**不是** MCP 服务端，也不提供另一个独立的公网 MCP 服务地址。

## 下载
**关联的原有发布：** [MCP/npm 启动器 0.2.4](../docs/SETUP.zh-CN.md) · [npm 发布页面](https://www.npmjs.com/package/@dns-data/remote) · [原有 GitHub v0.2.1 Release](https://github.com/DNSDATA/dns-data-mcp/releases/tag/v0.2.1) · [总发布页面](../RELEASES.zh-CN.md)。它们与 Windows EXE 使用独立版本号。


**[下载当前启用的 Windows 正式版 EXE](https://dns-data.com/console/api/v1/desktop-releases/download/active)** · [查看当前版本 SHA-256](https://dns-data.com/console/api/v1/desktop-releases/checksum/active)

以上地址会自动指向 DNS-DATA 后台**当前启用**的版本。如果启用版本切换，下载内容与校验值随之切换。单独的 [v0.1.27 版本链接](https://dns-data.com/console/api/v1/desktop-releases/download/0.1.27) 仅在该版本处于启用状态时可用，长期分享请使用上面的最新版本链接。

## 使用方法

1. 在 Windows 10/11 64 位电脑上，从官网下载并启动 EXE。
2. 登录 DNS-DATA 账号，完成设备绑定和相关鉴权。
3. 点击 **启动服务**，需要时可以停止或重启服务。
4. 在支持远程 MCP 的 AI 客户端中填写 `https://mcp.dns-data.com/mcp`，按提示完成 OAuth 授权。[详细 MCP 接入教程](../docs/SETUP.zh-CN.md)。

应用连接仍由账号权益、设备绑定和权限控制，不会因安装客户端而跳过鉴权。

## 开机自启设置

**“开机自启：已开启 / 已关闭”**为独立按钮，位于**“退出登录”正下方**，默认关闭。

开启后，用户**登录 Windows 后**客户端在后台启动，并尝试连接 MCP 服务；程序更新后会自动调整开机启动项的 EXE 路径，避免多开。它不属于 Windows 登录前就启动的系统服务。关闭后，每次重启需要用户自行打开客户端并点击启动服务。

## 应用更新与安全

用户端支持应用内检查更新、多线程分段下载、断点续传、SHA-256 完整性校验和按版本命名 EXE。新版成功安装启动后，自动清理旧 EXE、`.previous` 备份及已安装的下载缓存。

**v0.1.27 EXE SHA-256：**

```text
48e194ba34c188ebabf4bb2d56fbdab207b716c5de2b75a661f4969d10525cbb
```

在 PowerShell 中可用 `Get-FileHash -Algorithm SHA256 .\DNS-DATA-MCP-Windows-x64-v0.1.27.exe` 校验。下载其他版本时应使用对应版本的校验值。

## Windows 用户端版本记录

| 版本 | 更新内容 |
| --- | --- |
| **v0.1.27** · 2026-11-27 | 将开机自启按钮移至“退出登录”正下方，修复连接状态文字显示不全。 |
| v0.1.26 | 新增可选 Windows 登录后自启动，默认关闭，保留设备鉴权并适配更新后文件名。 |
| v0.1.25 | 修复检查更新、分段下载的 TLS 兼容问题。 |
| v0.1.24 | 更新成功后自动清理旧 EXE 和下载缓存。 |

**[返回总发布页面](../RELEASES.zh-CN.md)** · [返回 DNS-DATA MCP 首页](../README.zh-CN.md)

*此 GitHub 仓库主要提供集成文档，不托管专有 Windows EXE 源码或安装包；仓库的 MIT 许可不自动适用于单独分发的专有客户端。*

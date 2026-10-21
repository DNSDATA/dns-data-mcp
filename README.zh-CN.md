# DNS-DATA Remote｜让 AI 连接你授权的电脑

**让 AI 不只回答问题，还能在你的授权下读取文件、检查系统、执行命令和处理实际任务。**

[English](README.md) · [官方网站](https://dns-data.com/) · [每月免费额度](#免费套餐每月调用额度) · [中文接入指南](docs/SETUP.zh-CN.md) · [npm 启动器](https://www.npmjs.com/package/@dns-data/remote)

DNS-DATA 是通过 **Model Context Protocol（MCP）** 提供的远程设备连接服务。用户将自己的 Windows 或 macOS 电脑绑定到 DNS-DATA 账户后，可使用支持远程 MCP 的 AI 软件连接在线设备，进行获准的文件操作、系统检查和开发自动化。

**MCP 连接地址：** `https://mcp.dns-data.com/mcp`  
**协议：** Streamable HTTP · **认证：** OAuth 2.0  
**设备启动器：** `@dns-data/remote@0.2.1`

> **免费套餐每月额度：** 支持 **1 台设备，每月 10,000 次 DNS-DATA MCP 工具调用**，**次月自动恢复额度**（UTC 每月 1 日 00:00，北京时间 08:00）。[查看接入教程 →](docs/SETUP.zh-CN.md)

## DNS-DATA 能做什么？

| 场景 | 可以对 AI 说 |
| --- | --- |
| 查看电脑状态 | “使用 DNS-DATA 列出我绑定的电脑，看看哪些在线。” |
| 文件处理 | “读取我指定项目目录的 README，并总结当前项目结构。” |
| 系统排错 | “检查目标电脑的服务和进程，分析应用无法启动的原因。” |
| 编程与自动化 | “查看项目代码，提出修改建议，经过确认后运行构建命令。” |
| 查看已绑定电脑 | “检查我已连接电脑的进程状态，并分析异常情况。” |

具体工具权限由 AI 客户端、当前账号权益和设备端授权共同决定。**涉及删除、修改系统、执行高权限命令等操作，请先核实 AI 即将执行的指令。** [查看更多实用场景](docs/USE-CASES.zh-CN.md)。

## 三步完成接入

**第一步：在需要操作的电脑上启动服务。** 目前支持 Windows x64 和 macOS Apple Silicon。安装 Node.js 18 或更高版本，在终端或 PowerShell 中运行：

```bash
npx -y @dns-data/remote@0.2.1
```

按照提示注册或登录 DNS-DATA，核对设备信息和配对验证码后完成绑定。**保持启动窗口打开，设备即可保持连接；关闭窗口则设备下线。**

**第二步：在 AI 软件里添加远程 MCP。** 对于支持远程 MCP / Streamable HTTP 的客户端，输入：

```text
https://mcp.dns-data.com/mcp
```

完成 OAuth 登录与授权。ChatGPT、Claude、Gemini 及其他 AI 的实际接入界面会有所不同，取决于各自版本及 MCP 支持情况。

**第三步：进行第一次安全操作。**

> 使用 DNS-DATA 列出我的设备，并告诉我哪些电脑在线。

选择已在线、已授权的电脑后，再执行其他文件和系统操作。[中文图文接入说明 →](docs/SETUP.zh-CN.md)

## 免费套餐每月调用额度

- **可绑定设备：** 1 台 Windows 或 macOS 电脑。
- **每月调用额度：** **10,000 次 DNS-DATA MCP 工具调用**。
- **额度恢复：** **次月自动恢复额度**，按 UTC 自然月计算（每月 1 日 00:00 UTC，北京时间 08:00）。

当月额度用尽后，可等待次月自动恢复，再继续进行受调用额度限制的操作。

这里的调用次数仅指 DNS-DATA MCP 工具调用，不代表 ChatGPT、Claude 或其他 AI 平台的消息数、Token 或订阅额度。

[开始使用免费套餐 →](docs/SETUP.zh-CN.md)

## 连接与安全机制

- AI 软件通过 OAuth 获得你授权的 DNS-DATA 账号访问权限。
- 每台电脑必须经过独立绑定与授权；**仅添加 MCP 地址并不能直接访问电脑**。
- 电脑端主动连接 DNS-DATA 服务，通常不需要对公网开放设备入站端口。
- 只有设备在线、绑定有效、符合账户权益时，才能执行该设备上允许的工具操作。
- 可以关闭本地启动窗口，或在用户控制台解绑设备。

具有终端与文件写入权限的 AI 可以进行重要的系统变更。请只绑定自己拥有或获授权管理的电脑，妥善保管账户信息，在执行高风险命令前进行确认。[安全说明](SECURITY.md)。

## 文档与支持

- [完整中文接入教程](docs/SETUP.zh-CN.md) · [英文教程](docs/SETUP.md)
- [实际使用案例](docs/USE-CASES.zh-CN.md) · [English examples](docs/USE-CASES.md)
- [常见问题](docs/FAQ.zh-CN.md)
- [远程 MCP 配置](.mcp.json) · [MCP 服务元数据](server.json) · [Gemini 扩展清单](gemini-extension.json)
- [官网](https://dns-data.com/) · [联系我们](https://dns-data.com/zh/contact/) · [GitHub 问题反馈](https://github.com/DNSDATA/dns-data-mcp/issues)

本仓库公开不代表已经通过 MCP Registry 或 AI 应用市场的上架审核。

## 源码与许可说明

**本公开仓库内已发布的文档、接入配置示例及集成元数据**采用 [MIT License](LICENSE) 许可。可按该许可证使用、复制、修改和分发这些公开文件，须保留版权及许可声明。

**不在本仓库 MIT 许可范围内：** DNS-DATA 正式托管服务、专有后端与未公开源码、私有服务器配置、用户数据，以及在本仓库之外另行分发的软件或软件包。上述部分仍分别适用其自身的条款；公开仓库的 MIT 许可不代表将其开源。DNS-DATA 的名称与 Logo 商标权不因该许可证而授予。

反馈问题时，请勿发送密码、令牌、配对验证码、设备隐私信息或包含敏感数据的日志。

© 2026 Shenyang Youyida Network Technology Information Co., Ltd. 公开仓库资料适用上述许可，专有服务与组件保留相关权利。

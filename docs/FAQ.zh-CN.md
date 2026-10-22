# DNS-DATA Remote｜常见问题

[中文产品介绍](../README.zh-CN.md) · [接入教程](SETUP.zh-CN.md) · [免费套餐月度额度](../README.zh-CN.md#免费套餐每月调用额度) · [English FAQ](FAQ.md)

## 免费套餐每月有多少调用额度？次月怎样恢复？

免费套餐支持 **1 台已绑定设备、每月 10,000 次 DNS-DATA MCP 工具调用**。每个 UTC 自然月结束后，**次月自动恢复额度**（每月 1 日 00:00 UTC，北京时间 08:00）。

当月额度用完后，等待次月自动恢复即可，不需要重复注册账号。

## DNS-DATA 的月度额度是否包含 AI 的对话或 Token？

不包含。DNS-DATA MCP 工具调用次数与 ChatGPT、Claude、Codex 等 AI 平台的消息数、Token、API 费用和订阅限制分别计算。

## 已有 DNS-DATA 账户能继续使用吗？

可以。设备绑定和 AI 客户端的 OAuth 授权都使用同一个 DNS-DATA 账户。授权 AI 客户端并不等于已绑定新的电脑。

## 哪些 AI 可以连接？

支持远程 MCP / Streamable HTTP 及适当 OAuth 授权流程的客户端有机会兼容。ChatGPT、Claude、Gemini 和本地 AI 软件的可用能力可能因版本、套餐和界面而不同；仅支持本地 `stdio` MCP 的程序不能直接使用远程 HTTP 地址。

## 已完成 OAuth，但 AI 看不到在线电脑？

在需要操作的电脑上运行 `npx -y @dns-data/remote@0.2.3`，检查是否完成设备绑定，保持启动窗口打开。还需核对 AI 与设备使用的是同一个 DNS-DATA 账户。

## 仅仅添加 MCP 地址就能读取电脑文件吗？

不能。必须同时满足：账户 OAuth 授权、电脑完成独立绑定、设备在线、设备和用户权益有效，以及具体工具权限允许。

## 一台电脑能被多个 AI 软件使用吗？

支持远程 MCP 的 AI 客户端可以访问同一个 DNS-DATA 账户授权的设备。免费套餐可绑定 **1 台设备**。

## 是否需要公网 IP 或路由器端口转发？

标准连接由设备端主动发起，通常不需要给设备开公网入站端口或做路由器端口映射。

## 免费额度用完会删除账号或设备吗？

不会仅因本月额度用完而自动删除账户或已绑定设备。受额度限制的工具调用会在当月暂停，**次月自动恢复额度**后可继续使用。

## GitHub 公开仓库是不是正式服务端的开源代码？

不是。本仓库是产品文档及接入元数据；正式商业服务端实现不在此公开。

## GitHub 中有 server.json 就代表已进入官方 MCP Registry 吗？

不是。官方 Registry 发布、域名认证及各 AI 应用市场收录都需要另外申请或执行流程。

## 如何联系支持？

使用 [DNS-DATA 联系我们](https://dns-data.com/zh/contact/) 或 [GitHub Issues](https://github.com/DNSDATA/dns-data-mcp/issues)。请勿公开密码、OAuth 令牌、配对验证码、SSH 私钥、设备身份信息、敏感文件或私人日志。

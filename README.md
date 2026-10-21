# DNS-DATA Remote MCP

**Let your AI assistant work with your own Windows or macOS computer—not just answer questions.**

[简体中文](README.zh-CN.md) · [Official website](https://dns-data.com/) · [Monthly Free allowance](#free-monthly-allowance) · [Setup guide](docs/SETUP.md) · [npm launcher](https://www.npmjs.com/package/@dns-data/remote)

DNS-DATA is a hosted **remote Model Context Protocol (MCP)** service. Connect a compatible AI client to computers you have registered and authorized. From your AI conversation, you can inspect systems, work with files, run supported commands, and automate your own workflows.

**Remote MCP URL:** `https://mcp.dns-data.com/mcp`  
**Transport:** Streamable HTTP · **Sign-in:** OAuth 2.0  
**Device launcher:** `@dns-data/remote@0.2.1`

> **Free monthly allowance:** 1 registered computer and **10,000 DNS-DATA MCP tool calls each month**. The allowance automatically resets for the next month (00:00 UTC on the 1st). [Set up DNS-DATA →](docs/SETUP.md)

## See what your AI can do

| Use case | Example request |
| --- | --- |
| Inspect your computer | “List my connected computers and check which ones are online.” |
| Work with files | “Show me the files in my project folder and summarize the README.” |
| Troubleshoot | “Check the running services and help diagnose why my development app stopped.” |
| Develop and automate | “Inspect the project, propose a change, and run the approved build command.” |
| Inspect your registered device | “On my connected computer, check running processes and report any unexpected errors.” |

Commands, file access, and privileged operations depend on the connected client's capabilities and the permissions granted on the selected device. **Review AI-proposed commands before allowing destructive or sensitive changes.** See [more practical examples](docs/USE-CASES.md).

## Connect in three steps

**1. Start DNS-DATA on the computer you want to use.** Install Node.js 18+ on a supported **Windows x64** or **macOS Apple Silicon** device, then run:

```bash
npx -y @dns-data/remote@0.2.1
```

Sign in or register, follow the device pairing instructions, and confirm that the pairing code and computer details match. Keep the launcher window open while working; closing it disconnects the device.

**2. Add DNS-DATA to a compatible AI client.** In the client's remote MCP / Streamable HTTP settings, use:

```text
https://mcp.dns-data.com/mcp
```

Approve DNS-DATA OAuth authorization. The client may support automatic OAuth registration; setup details differ between ChatGPT, Claude, Gemini and other MCP-capable applications.

**3. Try a safe first request:**

> Use DNS-DATA to list my registered devices and tell me which are online.

Then select an online device before asking the AI to perform an authorized operation. [Full setup instructions →](docs/SETUP.md)

## Free monthly allowance

The **Free** tier includes:

- **1 registered Windows or macOS computer**.
- **10,000 DNS-DATA MCP tool calls each calendar month**.
- **Automatic allowance reset next month**, at 00:00 UTC on the 1st.

If this month's allowance is exhausted, quota-limited calls can resume after the next month's reset. Your DNS-DATA tool-call allowance does not increase the message, token or billing limits imposed by an AI provider.

[Try the Free tier: setup guide →](docs/SETUP.md)

## How access is controlled

- You sign in to your own DNS-DATA account and authorize the AI client through OAuth.
- Each target computer must be separately paired and registered to that account; an OAuth connection alone does not grant device access.
- The device-side runtime initiates the connection, so the standard workflow does not require exposing an inbound port on the computer.
- Operations are available only when the authorized device is online and the account's entitlements permit them.
- You can disconnect the runtime or unbind a registered device through the user console.

**Important:** An AI with terminal or file-writing access can make consequential changes. Only use computers you own or are authorized to administer; protect account credentials; verify commands and tool access. See [Security](SECURITY.md).

## Docs, integrations, and help

- [Detailed setup](docs/SETUP.md) · [中文接入教程](docs/SETUP.zh-CN.md)
- [Use cases](docs/USE-CASES.md) · [中文实例](docs/USE-CASES.zh-CN.md)
- [Troubleshooting and FAQ](docs/FAQ.md)
- [MCP server metadata](server.json) · [Remote MCP example](.mcp.json) · [Gemini extension manifest](gemini-extension.json)
- [Official website](https://dns-data.com/) · [Contact/support](https://dns-data.com/en/contact/) · [Report a documentation issue](https://github.com/DNSDATA/dns-data-mcp/issues)

Publishing a manifest in this repository **does not automatically publish DNS-DATA to an MCP Registry or AI marketplace**.

## Source availability

This **public repository contains documentation and integration metadata**, not the proprietary DNS-DATA hosted service or its server-side source code. See [LICENSE](LICENSE). Never post passwords, tokens, pairing codes, private device information, or sensitive logs in issues.

© DNS-DATA. All rights reserved.

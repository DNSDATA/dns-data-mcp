# DNS-DATA Remote — FAQ

[Overview](../README.md) · [中文常见问题](FAQ.zh-CN.md) · [Setup](SETUP.md) · [Free monthly allowance](../README.md#free-monthly-allowance)

## How does the Free monthly allowance work?

The Free tier currently provides **1 registered computer and 10,000 DNS-DATA MCP tool calls per calendar month**. The allowance **automatically resets for the next month** (on the 1st at 00:00 UTC).

If you exhaust this month's allowance, quota-limited operations can resume after the next month's reset. You do not need to create another account to receive the next monthly allowance.

## Does this MCP allowance cover AI messages or tokens?

No. DNS-DATA counts MCP tool calls separately from AI providers' message limits, token limits and API charges. The monthly allowance does not replace your AI provider's limits.

## Can I use my existing DNS-DATA account?

Yes. Use one account for pairing the device and authorizing compatible AI clients through OAuth. OAuth client registration is distinct from device binding.

## What AI clients are supported?

Clients that support **remote MCP / Streamable HTTP** and the appropriate OAuth authentication flow may be compatible. ChatGPT, Claude, Gemini and other applications expose MCP settings differently, and availability depends on their versions, plans and client capabilities. A local-only `stdio` MCP client cannot automatically use the hosted remote URL.

## Why does an AI client connect but no devices show as online?

OAuth authorization does not start the device runtime. On the target computer, run `npx -y @dns-data/remote@0.2.3`, complete pairing, and keep its window open. Confirm that you use the same DNS-DATA account and that the device entitlement is active.

## Does merely adding the MCP URL let an AI read my files?

No. Access requires account OAuth authorization plus a bound, authorized, online device. Allowed operations depend on tool access and operating-system permissions.

## Can several AI apps use the same computer?

Yes, when the clients support remote MCP and are authorized to the same account. Registered hardware counts against the device quota; multiple clients do not automatically create more device allowances.

## Do I need a public IP, VPN, or router port forwarding?

No public IP or incoming port forwarding is required for the normal device-initiated connection. The device must be able to reach DNS-DATA services over the network.

## Can I connect several Windows and macOS computers?

The Free tier supports **one registered device**. If you need to switch devices, unbind the previous device in your account console before binding another one.

## What if the monthly quota is exhausted?

Quota-limited tool calls pause until the next UTC calendar month's allowance is automatically restored. Reaching the monthly allowance does not by itself delete your account or registered device.

## Is the hosted service open source?

No. The public GitHub repository contains documentation and integration metadata. The hosted server and its underlying business logic are proprietary.

## Does publishing `server.json` list DNS-DATA in the official MCP Registry?

No. Registry publication, domain verification, and marketplace inclusion are separate procedures.

## Where can I get support or report a problem?

Use [DNS-DATA Contact](https://dns-data.com/en/contact/) or [GitHub Issues](https://github.com/DNSDATA/dns-data-mcp/issues) for non-sensitive documentation and integration issues. **Never** post passwords, OAuth tokens, pairing codes, SSH private keys, device identifiers, confidential file contents or private logs publicly.

# DNS-DATA Remote — Setup Guide

[中文说明](../README.zh-CN.md) | [Overview](../README.md)

## Requirements

- DNS-DATA account on https://dns-data.com/
- A Windows x64 or macOS Apple Silicon computer you own or are authorized to access
- Node.js 18 or newer for the official npm launcher
- A compatible AI client that supports remote MCP over Streamable HTTP and OAuth

## Connect a computer

1. Open PowerShell (Windows) or Terminal (macOS).
2. Run:

   ```bash
   npx -y @dns-data/remote@0.2.3
   ```

3. If prompted, sign in with your existing account and complete the browser-based device pairing confirmation.
4. Keep the launcher running to make the computer available. Closing its window takes the device offline.

The launcher is the **device-side connector**, not the hosted MCP endpoint. No public IP address or incoming port forwarding is required for the standard workflow.

## Connect an AI client

In your AI client's remote MCP connector settings, enter:

- **Name:** `DNS-DATA`
- **URL:** `https://mcp.dns-data.com/mcp`
- **Transport:** Streamable HTTP / HTTP, if selectable
- **Authentication:** OAuth sign-in
- **OAuth client registration:** Automatic/DCR, if offered

When the DNS-DATA sign-in page opens, authenticate using your registered account and approve access. A client OAuth identity is separate from the user's registered device entitlement.

After connecting, start with a device-list request. Confirm the target device is online before asking the AI to perform file or system operations.

### Example remote MCP configuration

```json
{
  "mcpServers": {
    "dns-data": {
      "type": "http",
      "url": "https://mcp.dns-data.com/mcp"
    }
  }
}
```

AI applications differ in the supported connector UI and configuration syntax. Use each client's official instructions when the example is not directly accepted.

## Safety

- Only bind computers you own or have permission to administer.
- Protect your DNS-DATA account and approve OAuth authorization requests deliberately.
- Disconnect the device service when remote access is no longer required.
- Do not paste passwords, bearer tokens, private keys, or pairing codes into public issues.

# DNS-DATA Windows desktop user client

**Standalone Windows user application** · Windows 10/11 (x64) · **v0.1.27** · Updated November 27, 2026

[简体中文](README.zh-CN.md) · **[All DNS-DATA releases](../RELEASES.md)** · [Official Windows download page](https://dns-data.com/en/download/) · [GitHub Releases overview](https://github.com/DNSDATA/dns-data-mcp/releases)

DNS-DATA Windows is a separate graphical **user-side application** for connecting a Windows computer to the DNS-DATA Remote MCP service. You can use it without the command-line npm launcher. It is **not** the MCP server and does not expose an independent public MCP endpoint.

## What the Windows user client does

The DNS-DATA Windows user client provides a graphical way to connect a Windows 10/11 computer to the hosted DNS-DATA Remote MCP service, without installing Node.js or launching a command-line tool. It is intended for Windows users who want straightforward device and connection management and controlled access from compatible AI assistants.

Main capabilities:

- **Account and device pairing:** Sign in and complete device registration and identity verification.
- **Service controls:** Start, stop, or restart the MCP connection using the application interface.
- **AI-assisted computer access:** With appropriate authorization and device permissions, compatible AI clients can inspect system information, work with files, and execute supported commands.
- **Optional Windows auto-start:** Turn on or off automatic startup after Windows sign-in; disabled by default.
- **In-app updates:** Version checking, parallel HTTP range downloads, resume support, and SHA-256 verification.
- **Access controls:** Existing account authentication, device binding, and permission checks remain in effect.

The Windows graphical client and the MCP/npm command-line launcher connect to the same hosted Remote MCP service, but serve different users and have separate version numbers.

## Download
**Related releases:** [MCP/npm launcher 0.2.4](../docs/SETUP.md) · [npm package](https://www.npmjs.com/package/@dns-data/remote) · [Original GitHub integration Release v0.2.1](https://github.com/DNSDATA/dns-data-mcp/releases/tag/v0.2.1) · [All DNS-DATA releases](../RELEASES.md). These are separate releases, not Windows EXE versions.


**[Download the latest active Windows EXE](https://dns-data.com/console/api/v1/desktop-releases/download/active)** · [Official checksum (SHA-256)](https://dns-data.com/console/api/v1/desktop-releases/checksum/active)

The links above always follow the version **enabled** in DNS-DATA's official release manager. The version-specific [v0.1.27 download](https://dns-data.com/console/api/v1/desktop-releases/download/0.1.27) works only while that version remains enabled. Use the "active" link for a permanent current-version address.

## How to use it

1. Download the EXE from the official website and start it on Windows 10/11 x64.
2. Sign in to DNS-DATA and complete the required device pairing and verification.
3. Click **Start service**. The application also provides stop and restart controls.
4. Connect your supported AI client to the hosted remote MCP endpoint `https://mcp.dns-data.com/mcp` using its OAuth authorization workflow. [MCP connection guide](../docs/SETUP.md).

Service access is limited by account entitlements, device binding, and permissions; simply installing the Windows app does not bypass authorization.

## Windows startup setting

The independent **Auto-start: Enabled / Disabled** button sits directly **below Sign out**. The default is **disabled**.

When enabled, the app launches and attempts to start the MCP service **after you sign in to Windows**. It uses a per-user Windows startup entry, updates the executable path after app updates, and avoids launching duplicate client instances. It is **not** a Windows service that runs before login. When disabled, start the client and service manually after restarting.

## Downloads and in-app updates

The Windows app supports update detection, multithreaded HTTP range downloads, resume, SHA-256 verification, and versioned executable filenames. After the new version has launched, obsolete executables, `.previous` files, and installed download caches are removed. Device authentication still applies.

**v0.1.27 EXE SHA-256:**

```text
48e194ba34c188ebabf4bb2d56fbdab207b716c5de2b75a661f4969d10525cbb
```

Check a downloaded file in PowerShell with `Get-FileHash -Algorithm SHA256 .\DNS-DATA-MCP-Windows-x64-v0.1.27.exe`. Use the version's own checksum when the active release changes.

## Windows desktop release notes

| Version | Change |
| --- | --- |
| **v0.1.27** · 2026-11-27 | Moves the startup control to a full-width independent button below Sign out; fixes clipped service-status text. |
| v0.1.26 | Adds optional logon auto-start (off by default), retaining device authorization and maintaining the startup path after updates. |
| v0.1.25 | Fixes TLS compatibility for update checks and parallel downloads. |
| v0.1.24 | Uses versioned EXE filenames and cleans old binaries and update caches after successful updates. |

[Back to the all-products release index](../RELEASES.md) · [Back to DNS-DATA Remote MCP](../README.md)

*Windows executable binaries and proprietary application source code are distributed separately from this repository. The repository's MIT license does not grant a license to proprietary Windows client code.*

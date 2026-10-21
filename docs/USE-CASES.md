# Practical DNS-DATA Remote MCP examples

[Overview](../README.md) · [中文使用案例](USE-CASES.zh-CN.md) · [Setup guide](SETUP.md)

These sample prompts illustrate what you can ask a **compatible remote-MCP-enabled AI client** to do through DNS-DATA. Results depend on the **bound, online target device** and its permitted tools. Start with read-only operations. Never execute unreviewed commands on critical systems.

## 1. Verify your connection

> Use DNS-DATA to list the computers registered to my account. Show which are online. Do not modify anything.

**Expected workflow:** The AI queries available devices and reports their status. OAuth authorization alone does not turn a computer on or connect its runtime.

## 2. Inspect a development workstation

> On my selected Windows computer, show the OS details, running processes, and available services. Only inspect; do not stop or change services.

Useful when troubleshooting a local development environment. Read-only checks should precede any modification.

## 3. Understand a project

> On my selected computer, list the files in the project directory I specify, read its README and configuration documentation, and summarize how it runs. Do not reveal secret file contents.

Restrict the requested directory, especially if it contains credentials, customer information or deployment secrets.

## 4. Prepare a build with human approval

> Inspect the source files and propose a build/test command. Explain its effects and ask for my confirmation **before** running it or writing any files.

Use a non-production test environment. DNS-DATA grants access to tools; it does not provide unlimited AI model compute or ensure a script is safe.

## 5. Compare two registered computers

> List my online devices. After I choose a Windows computer and a Mac, separately collect their basic system information and summarize the differences without changing settings.

The Free tier permits one bound computer. For your first test, select that computer and inspect its status without changing settings.

## 6. Investigate a stopped service

> Check the service status and relevant process information on the selected device. Explain potential causes, and propose a recovery plan. **Do not restart, disable, or delete anything without approval.**

Privileged command execution depends on the system and device-side permissions. Some commands may require additional authorization.

## Next steps

- [Start with the official launcher and remote MCP URL](SETUP.md).
- [Read the FAQ](FAQ.md).
- [Read how the Free monthly allowance resets](../README.md#free-monthly-allowance).

**Security:** Only access machines you are authorized to administer. Treat AI-suggested shell commands as untrusted until reviewed. Never paste credentials into GitHub issues or publish private logs.

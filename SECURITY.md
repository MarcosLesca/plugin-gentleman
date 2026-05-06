# Security Policy

## Supported Versions

Only the latest stable release receives security fixes.

| Version | Supported |
|---------|-----------|
| latest  | ✅        |
| older   | ❌        |

## Reporting a Vulnerability

Do **not** open a public GitHub issue for security vulnerabilities.

Report security issues privately through GitHub Security Advisories:

https://github.com/IrrealV/plugin-gentleman/security/advisories/new

If the advisory flow is unavailable, contact the maintainers directly through GitHub.

## What to Include

- A clear description of the vulnerability.
- Steps to reproduce.
- The affected version and OpenCode version.
- Your operating system.
- The potential impact.
- Any mitigation or workaround you found.

## Response Timeline

- **Acknowledgement:** best effort within 48 hours.
- **Initial assessment:** best effort within 5 business days.
- **Fix target:** within 30 days for critical/high severity when a fix is viable.
- **Disclosure:** coordinated after a fix is available.

## Scope

Plugin Gentleman is a local OpenCode TUI plugin. Its expected attack surface is small, but reports are welcome when they affect user safety or local environment integrity.

In scope:

- Path traversal or unsafe file writes in plugin/runtime behavior.
- Injection risks in rendered terminal content or configuration handling.
- Exposure of local environment, provider, session, or cost data beyond intended UI display.
- Denial-of-service behavior caused by malformed configuration or untrusted runtime values.
- Package contents that unexpectedly include sensitive or user-specific files.

Out of scope:

- Issues requiring physical access to the user's machine.
- Issues requiring an attacker to already control the user's home directory or OpenCode config.
- Social engineering, phishing, or unrelated third-party service issues.
- Cosmetic rendering bugs without a security impact.

## Recognition

We recognize responsible disclosures in release notes when appropriate and when the reporter wants public credit.

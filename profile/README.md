<p align="center"><img src="https://raw.githubusercontent.com/go-aiquota/brand/main/social/go-aiquota.png" alt="go-aiquota" width="720"></p>

<h1 align="center">go-aiquota</h1>
<p align="center">A cross-platform menu-bar app that monitors AI usage quotas across multiple accounts in parallel.</p>
<p align="center">
  <a href="https://go-aiquota.github.io/docs/"><img src="https://img.shields.io/badge/docs-mkdocs--material-0A6E96?style=flat-square&logo=materialformkdocs&logoColor=white" alt="docs"></a>
  <img src="https://img.shields.io/badge/repos-3-0079A8?style=flat-square" alt="repos">
  <img src="https://img.shields.io/badge/Go-1.26.4-00ADD8?style=flat-square&logo=go&logoColor=white" alt="Go">
  <img src="https://img.shields.io/badge/license-BSD--3--Clause-0A6E96?style=flat-square" alt="license">
</p>

---

## What is this?

`go-aiquota` is a cross-platform menu-bar app that watches AI usage quotas — session and weekly limits — across multiple accounts at once. Each provider (Claude today, others as plugins are added) is a separate subprocess talking a small [hashicorp/go-plugin](https://github.com/hashicorp/go-plugin) gRPC contract, so adding a provider means writing a plugin, not forking the host.

Onboarding an account drives a real, isolated embedded browser straight to the provider's own login page (WKWebView on macOS, go-webengine elsewhere) — no manual cookie copying, no devtools network-tab archaeology. Only the resulting cookies and the account's organization UUID ever reach the provider plugin; a credential is never logged and lives only in the OS keyring.

## Repositories (3)

| Module | Kind | What it is | API |
|---|---|---|:--:|
| [`tray`](https://github.com/go-aiquota/tray) | host app | The menu-bar host app — per-account tray items, plugin manager, isolated onboarding. | [ref](https://pkg.go.dev/github.com/go-aiquota/tray) |
| [`proto`](https://github.com/go-aiquota/proto) | contract | The QuotaProvider gRPC contract, plus Secret/redact credential-safety types. | [ref](https://pkg.go.dev/github.com/go-aiquota/proto) |
| [`plugin-claude`](https://github.com/go-aiquota/plugin-claude) | provider plugin | The reference QuotaProvider plugin — Claude Max / Team Premium / Team Standard. | [ref](https://pkg.go.dev/github.com/go-aiquota/plugin-claude) |

> This list reflects the repos that actually exist in the org.

## Links

- 📖 Docs — <https://go-aiquota.github.io/docs/>
- 🌐 Site — <https://go-aiquota.github.io/>
- 🎨 Brand assets — <https://github.com/go-aiquota/brand>

---
<p align="center"><sub>Branding in <a href="https://github.com/go-aiquota/brand">go-aiquota/brand</a>.</sub></p>

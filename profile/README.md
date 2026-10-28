# opzero1

Tools that make OpenCode V2 agents durable, visible and safe.

This is Afif's open-source workshop for [OpenCode](https://opencode.ai) and AI-agent tooling. Most of it started as something I needed day to day: agents that keep working after a restart, background workers you can open and inspect, browser control that doesn't need a separate headless stack, and a permission layer that doesn't ask about every `git status`.

Expect early-stage software; each README states what works today and which OpenCode version it targets.

## Agents

| Repo | What it does |
| --- | --- |
| [open-dot](https://github.com/opzero1/open-dot) | A durable personal agent on OpenCode V2. Give a dot a name and a purpose, reopen it from anywhere, and it follows up, delegates and talks to other dots on its own time. |
| [threads](https://github.com/opzero1/threads) | Background agents for OpenCode V2: visible worker sessions that report back with a verdict, and parallel workflows that survive restarts. |

```sh
opencode plugin add @op1/threads
```

## Browser & desktop control

| Repo | What it does |
| --- | --- |
| [browser-control](https://github.com/opzero1/browser-control) | Connects an agent to your Chrome through an MCP server, a Chrome extension and a native messaging host. Observed page actions, tab ownership, screenshots and isolated Chrome for Testing leases. |
| [chrome-devtools-cli](https://github.com/opzero1/chrome-devtools-cli) | Small Rust CLI that talks to an already-running Chrome over the DevTools Protocol, one command in and one result out. Fork of [aeroxy/chrome-devtools-cli](https://github.com/aeroxy/chrome-devtools-cli). |

```sh
npx -y @op1/browser-control install
```

```sh
brew tap opzero1/chrome-devtools-cli
brew install chrome-devtools
```

## OpenCode V2 plugins

| Repo | What it does | Install |
| --- | --- | --- |
| [open-guardian](https://github.com/opzero1/open-guardian) | LLM permission judge: a fast model reviews each escalated action against a written policy and allows, denies or asks you. Errors always fall back to asking. | `"plugins": ["open-guardian"]` |
| [opencode-subagent-model](https://github.com/opzero1/opencode-subagent-model) | Shows a subagent session's agent and model above the composer. | `opencode plugin add @op1/opencode-subagent-model` |
| [op-session-id](https://github.com/opzero1/op-session-id) | `/session-id` copies the current session ID and confirms with a toast. | `"plugins": ["op-session-id@0.2.0"]` |

## Utilities

| Repo | What it does |
| --- | --- |
| [open-pass](https://github.com/opzero1/open-pass) | Use saved 1Password credentials in CLI programs and background browser tabs through one reusable local SDK daemon. |
| [token-calc](https://github.com/opzero1/token-calc) | Local dashboard and terminal UI for token usage and estimated cost across Claude Code, Codex, Gemini, OpenCode, Amp and Pi. Nothing is uploaded. |
| [warmplane](https://github.com/opzero1/warmplane) | Local control plane that keeps MCP sessions warm behind one process and exposes a compact, lazy tool surface. Fork of [Warmplane/warmplane](https://github.com/Warmplane/warmplane). |
| [gif-bar](https://github.com/opzero1/gif-bar) | macOS menu bar app for searching Giphy and copying Slack-friendly GIF links. |
| [homebrew-tap](https://github.com/opzero1/homebrew-tap) | Homebrew tap for opzero1 apps (`brew tap opzero1/tap`). |

## Earlier work

Built for OpenCode V1 or replaced by the projects above. Kept public for reference.

| Repo | What it was |
| --- | --- |
| [op1](https://github.com/opzero1/op1) | OpenCode harness with an installer, agent templates and workspace plugins (`bunx @op1/install`). |
| [goals](https://github.com/opzero1/goals) | Codex-style `/goal` command: a durable per-session objective with token budgets (`@op1/goals`). |
| [op-loading](https://github.com/opzero1/op-loading) | Terminal tab title spinner while OpenCode is busy, and a blinking `?` while it waits for you. |
| [op-usage](https://github.com/opzero1/op-usage) | Codex rate-limit usage shown beside the OpenCode prompt. |
| [op-slack](https://github.com/opzero1/op-slack) | OpenCode plugin with Slack read and write tools through your own Slack app. |
| [multiplexer](https://github.com/opzero1/multiplexer) | Terminal multiplexer prompt files and a shell helper for launching Codex sessions. |

# Devcontainer Base

A sandboxed development environment for running [Claude Code](https://claude.ai/code) autonomously in bypass-permissions mode. The container isolates Claude from the host filesystem while providing a full-featured development toolchain, persistent volumes, and cloud integrations.

Inspired by Trail of Bits' [claude-code-devcontainer](https://github.com/trailofbits/claude-code-devcontainer), which was purpose-built for safe autonomous Claude Code operation during security audits. This repo adapts their approach with additional tooling and integrations for day-to-day development workflows.

## What's Included

### AI
- [Claude Code](https://claude.ai/code) CLI with marketplace plugins (Anthropic Skills, Trail of Bits Skills)
- [RTK](https://github.com/rtk-ai/rtk) (Rust Token Killer) — token-optimized CLI proxy

### Languages & Runtimes
- **Python 3.13** via [UV](https://github.com/astral-sh/uv) (fast package/project manager)
- **Node.js v22** via [fnm](https://github.com/Schniz/fnm) (Fast Node Manager)

### Cloud
- **Google Cloud CLI** (`gcloud`) with persistent config volume

### Search & Navigation
- [ripgrep](https://github.com/BurntSushi/ripgrep) — fast regex search
- [fzf](https://github.com/junegunn/fzf) — fuzzy finder
- [ast-grep](https://ast-grep.github.io/) — AST-based code search
- [fd](https://github.com/sharkdp/fd) — fast file finder

### Git
- [git-delta](https://github.com/dandavison/delta) — enhanced diffs with syntax highlighting
- [GitHub CLI](https://cli.github.com/) (`gh`)

### Shell & Terminal
- Zsh with [Oh My Zsh](https://ohmyz.sh/)
- tmux with 200k line history, mouse support, and vi keys
- Persistent shell history across container rebuilds (200k lines)

### Editors & Utilities
- nano, vim, jq, curl, unzip
- Build tools (build-essential)
- Network tools (dnsutils, ipset, iptables, iproute2)
- [bubblewrap](https://github.com/containers/bubblewrap) (sandboxing support)

### VS Code Extensions
- Claude Code
- dbt Power User
- Rainbow CSV
- YAML

## Key Features

- **Bypass-permissions mode** — Claude Code runs without interactive approval prompts
- **Onboarding bypass** — skips the Claude Code setup wizard when OAuth token is set
- **Persistent volumes** — shell history, Claude config, GitHub config, and gcloud config survive container rebuilds
- **Host gitconfig** — your git identity is shared read-only from the host
- **Network capabilities** — NET_ADMIN and NET_RAW for security testing scenarios

## Setup

1. Copy `.devcontainer/.env.example` to `.devcontainer/.env`
2. Fill in your tokens:
   - `CLAUDE_CODE_OAUTH_TOKEN` — Claude Code OAuth token
   - `GH_TOKEN` — GitHub personal access token
3. Open this directory in VS Code
4. When prompted, click **Reopen in Container** (requires the [Dev Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) extension)

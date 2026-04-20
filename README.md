# Devcontainer Base

A sandboxed development environment for running [Claude Code](https://claude.ai/code) autonomously in bypass-permissions mode. The container isolates Claude from the host filesystem while providing a full-featured development toolchain, persistent volumes, and cloud integrations.

Inspired by Trail of Bits' [claude-code-devcontainer](https://github.com/trailofbits/claude-code-devcontainer), which was purpose-built for safe autonomous Claude Code operation during security audits. This repo adapts their approach with additional tooling and integrations for day-to-day development workflows.

## What's Included

- [Claude Code](https://claude.ai/code) CLI with marketplace plugins and [RTK](https://github.com/rtk-ai/rtk) token proxy
- **Python 3.13** via [UV](https://github.com/astral-sh/uv) and **Node.js v22** via [fnm](https://github.com/Schniz/fnm)
- **Google Cloud CLI** with persistent config volume
- **GitHub CLI** (`gh`)
- Zsh with Oh My Zsh, tmux, and persistent shell history (200k lines)
- Search tools: ripgrep, fzf, ast-grep, fd
- Git enhancements: [git-delta](https://github.com/dandavison/delta) for diffs

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

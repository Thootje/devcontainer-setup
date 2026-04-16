# Devcontainer Setup

A Claude Code devcontainer for development at Xebia.

## What's Included

### Tooling
- **Python**: 3.13 via [UV](https://github.com/astral-sh/uv) package manager
- **Node.js**: v22 via [fnm](https://github.com/Schniz/fnm) (Fast Node Manager)
- **Cloud**: Google Cloud CLI
- **AI**: Claude Code CLI with marketplace plugins (Anthropic Skills, Trail of Bits)
- **Shell**: Oh My Zsh with persistent history (200k lines)
- **Search**: ripgrep, [fzf](https://github.com/junegunn/fzf), [ast-grep](https://ast-grep.github.io/)
- **Git**: [git-delta](https://github.com/dandavison/delta) for diffs
- **Terminal**: tmux with mouse support and vi keys

### MCP Integrations
- Notion
- Slack
- Readwise
- Atlassian

### Key Features
- Persistent shell history across container rebuilds (200k lines)
- Obsidian vault mounted at `/obsidian`
- Shared gcloud config volume across containers
- Auto-bypass Claude Code onboarding when OAuth token is set
- Claude Code bypass-permissions mode enabled by default

## Setup

1. Copy `.devcontainer/.env.example` to `.devcontainer/.env`
2. Fill in your tokens:
   - `CLAUDE_CODE_OAUTH_TOKEN` — Claude Code OAuth token
   - `ATLASSIAN_API_TOKEN` — Atlassian API token
   - `GH_TOKEN` — GitHub personal access token
   - `DBT_CLI_TIMEOUT` — dbt CLI timeout in seconds (default: 600)
3. Open this directory in VS Code
4. When prompted, click **Reopen in Container** (requires the [Dev Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) extension)

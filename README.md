# My Skills`r`n# My Skills

Personal Codex skills and tool sources. Skills in `.agents/skills/` are loaded by Codex when this repository is opened as a trusted project.

## Installed skills

- `frontend-design` — distinctive visual direction for frontend work. Source: `sources/anthropic-skills/skills/frontend-design`.
- `ui-ux-pro-max` — UI/UX recommendations, searchable design data and stack-specific guidance. Installed with the upstream CLI; update through `uipro update` after refreshing the package.
- `agent-reach` — read-only platform access skill. Its runtime is not installed yet; see `sources/agent-reach/INSTALL.md`.

## gstack

`sources/gstack` tracks the upstream engineering workflow repository as a Git submodule. Its Codex support is experimental. The full setup requires Bun 1.4.2+ and builds browser tools; run `./setup --host codex` from that source directory in Git Bash or WSL after installing Bun. Setup may update Codex hooks and global configuration. Review its current setup prompts and docs before opting in. Until setup is run, gstack's skills are not installed as active Codex skills. The checkout is intentionally not duplicated under `.agents/skills/` so updates come from the submodule.

## Playwright MCP

Playwright MCP is an MCP server rather than a skill. This repo tracks its source at `sources/playwright-mcp`. To enable it in Codex, merge the following entry into `%USERPROFILE%\.codex\config.toml` (after installing Node.js 20+):

```toml
[mcp_servers.playwright]
command = "npx"
args = ["-y", "@playwright/mcp@latest"]
```

Restart Codex after changing MCP configuration.

## Update sources

```bash
git submodule update --remote --merge
```

After updating Anthropic skills, recopy `skills/frontend-design` into `.agents/skills/frontend-design`. To refresh UI UX Pro Max, update/install its CLI and run `uipro update --global` for a global install, or reinstall into this repo with `uipro init --ai codex --force`.

## GitHub

Create an empty GitHub repository under your account, then add it as `origin` and push this repository. No remote has been configured yet, so it remains local and private on this machine.
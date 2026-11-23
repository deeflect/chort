---
name: chort
description: Design UI boards in real HTML and CSS on the local chort macOS canvas over MCP, run check_design audits, resolve canvas comments, and export JSX/Tailwind. Use when designing screens, components, landing pages, or iterating on canvas feedback with chort.
metadata:
  version: 0.1.6
  author: deeflect
  source: https://chort.design
---

# chort

chort is a local HTML and CSS design canvas for coding agents on macOS (Apple silicon). Files live on disk in `~/Documents/chort` so Git is your history.

## Install and connect

1. Download the signed beta DMG from https://github.com/deeflect/chort/releases/latest and launch chort (the local MCP server listens on `http://127.0.0.1:4117`).
2. Connect your agent:

```bash
# Claude Code
claude mcp add --scope user --transport http chort http://127.0.0.1:4117/mcp/claude-code

# Codex
codex mcp add chort --url http://127.0.0.1:4117/mcp/codex
```

## Workflow

1. Inspect the active file and selection (`get_basic_info`, `get_tree_summary`, `get_selection`).
2. Create an artboard (`create_artboard`) and build sections with real HTML and CSS (`write_html`) using Tailwind v4 CSS custom property tokens (`get_tokens`, `set_tokens`).
3. Run `check_design` after each section to catch overflow, contrast, alignment, and tiny text as text before taking screenshots (`get_screenshot`).
4. Read and resolve user canvas comments (`list_comment_threads`, `set_comment_thread_status`) and mark completed nodes (`finish_working_on_nodes`).
5. Export clean JSX/Tailwind (`get_jsx`) or static assets (`export`, `export_handoff`).

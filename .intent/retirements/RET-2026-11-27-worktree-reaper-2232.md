---
title: Worktree reaper pass 2026-11-27 22:32
type: retirement-manifest
maturity: final
created: 2026-11-27
---

# Worktree reaper pass, 2026-11-27 22:32

The hourly worktree reaper (org-design-tooling `repo-kit/worktree_reaper.py`, LaunchAgent com.brien.worktree-reaper) retired these linked worktrees of this repo. Each one's work was already on main, nothing had touched it within the idle window, and no running process or recent Claude session was using it. Nothing was lost: each tip is pinned by a pushed archive tag, and each uncommitted file was kept as listed. The worktree folder and its local branch were removed after this record landed.

## fieldbook-site-wt-2026-11-23-site-wording-2026-11-23

- Path: `~/Workspaces/Core/products/fieldbook-site-wt-2026-11-23-site-wording-2026-11-23` (kit worktree)
- Branch: `agent/claude/2026-11-23-site-wording-2026-11-23`, tip `a6917a03`, last commit 2026-11-23
- Tag: `archive/agent/claude/2026-11-23-site-wording-2026-11-23-2026-11-27`
- Landing on main: tip is on origin/main
- Idle: 96.8 hours when retired
- Residue: nothing uncommitted
- Commits not on main by hash: none
- Files those commits touched: none
- Recover: `git checkout -b agent/claude/2026-11-23-site-wording-2026-11-23 archive/agent/claude/2026-11-23-site-wording-2026-11-23-2026-11-27`

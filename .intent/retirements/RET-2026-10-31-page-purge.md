---
title: "History rewrite: client names in page content purged from public history"
type: retirement
maturity: final
created: 2026-10-31
kind: history-rewrite
repo: git@github.com:theparlor/fieldbook-site.git
repo_visibility: public
holds_it: bundle ~/.local/state/retired-history-bundles/fieldbook-site-pre-page-purge-2026-10-31.bundle (git bundle verify passed 2026-10-31, sha256 dcedc4bb3bfc82ed29752a32d90162ae12bc1f879cd49cf78a08184b56978c6b, 308910 bytes, every ref as of the rewrite); local tag archive/pre-page-purge-2026-10-31 in the primary checkout (never pushed)
tip_before: 4cc855cb9f67007ebd61c60b1b5a87ae4d523503
tip_after: 7e815bedfca63d82ae37611b8f2d3ee4b0ebb124
commits_before: 88
commits_after: 88
page_lines_rewritten: 2
paths: index.html
---

# History rewrite: client names in page content purged from public history

## Why

Page content in this public repo (`index.html`) named a client engagement in its provenance wording from
2026-06-05. The wording was fixed going forward on 2026-10-02 ("Neutralize client names" commit), and the
2026-10-03 ruling on the history-purge decision surface (WS-DDR-156) left the old public commits in place:
"forward-fix the other 15 site repos". The 2026-10-31 purge of the vendored kit's comments
(`RET-2026-10-31-name-purge.md`, Brien: "address without permanently losing data") left these page lines as the only client names in this
repo's published history, and said so.

Brien, 2026-10-31, told that older names remain in page history in this repo and one other, which the
2026-10-03 forward-fix-only ruling had left alone: "i want these resolved". That supersedes the 2026-10-03 ruling for these
two repos. The private sources keep their wording (KF-01, KF-05); this is redaction at egress (KF-06) on a
public repo, with the bundle below so nothing is lost (KF-02).

## What changed

- `git filter-repo --replace-text` over a fresh mirror clone, 2026-10-31: 2 diff line(s) across branches and
  tags carried the old provenance phrase; each became the exact forward-fixed wording main already carries,
  so the tip's tree is unchanged. Commit messages, authors, dates and every other blob are unchanged.
- Every branch and tag was force-pushed explicitly; `refs/pull/*/head` cannot be pushed and stay as GitHub
  holds them. Remote main confirmed at 7e815bedfca6 after the push.
- Rulesets at push time: 23693635:no-entire-checkpoint-refs:no; classic branch protection: none.
  Nothing refused the push, so nothing was paused.
- GitHub Pages after the push: built (build of 7e815bedfca6 at 2026-10-31T14:44:17Z).

## Recover

Nothing here is gone. The bundle holds every ref of the repo as it stood on GitHub before this rewrite
(after the kit-comment rewrite earlier the same day), outside the repo; the local tag pins the last
pre-rewrite main in the primary checkout.

```bash
git bundle verify ~/.local/state/retired-history-bundles/fieldbook-site-pre-page-purge-2026-10-31.bundle
git clone ~/.local/state/retired-history-bundles/fieldbook-site-pre-page-purge-2026-10-31.bundle fieldbook-site-pre-page-purge-2026-10-31
git -C <primary> show archive/pre-page-purge-2026-10-31:index.html
```

The bundle and the tag are never pushed. Re-publishing the old history would reintroduce the names and
needs an explicit ruling.

## Residual, stated plainly

GitHub keeps the old commits reachable by SHA, through cached views and through the `refs/pull/N/head`
refs of every merged PR, until its own garbage collection runs. Forks and third-party caches may hold
copies. Full removal from GitHub needs a support request, and that request is Brien's call.

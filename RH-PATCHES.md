# ReviewHerd patches

This is the ledger of the ReviewHerd fork of `openai/codex` (`chinaryov/codex`).
Branch `rh/main` is the upstream release below plus the patches listed here.
Nothing else may differ from upstream.

Upstream: https://github.com/openai/codex
Upstream base: rust-v0.165.0 360319d8dee62d87e2d59fc0c21805d79519cfed

## Rules

The `ledger` check of `.reviewherd.yaml` enforces these on every candidate commit:

- `Upstream base:` holds the upstream tag and the full commit it peels to.
  The commit must equal the tag's commit in upstream and be an ancestor of `HEAD`.
- `git diff --name-only --no-renames -z <base commit> HEAD` may list only
  `RH-PATCHES.md`, `.reviewherd.yaml` and the files of the patches below.
  A rename shows as a delete plus an add, so both paths must be listed.
- A sync with a newer upstream release merges the new tag and bumps
  `Upstream base:` in the same PR.

Each patch is one `### ` section under `## Patches` with this shape:

```text
### P-1: Short title

Why: one or two sentences.
Upstream: link to the upstream issue or PR, or "none".
Files:
- `codex-rs/some-crate/src/file.rs`
```

The `Files:` list is a run of `` - `path` `` lines, one path per line,
relative to the repository root. The list ends at the first other line.
Only a `### P-<n>: <title>` section with `Why:` and `Upstream:` lines
authorizes its files. The check fails on a `Files:` line outside such a
section and on a `### ` section under `## Patches` of another shape.

Fenced blocks follow CommonMark: a block opened by a run of backticks or
tildes ends only at a run of the same character, at least as long, with
nothing after it but blanks. Nothing inside a fence counts. To keep the
parse unambiguous, the check also fails on a heading or fence indented by
spaces, on HTML, on a `===` or `---` line right under a line of text, and,
under `## Patches`, on a block quote or a list other than a `Files:` list.

## Patches

None yet.

# Skill lifecycle and repo map

How the skills are organised, and everything that must stay in sync when a skill is added, renamed, removed, or reorganised. The docs-page branch lives in [writing-docs.md](./writing-docs.md); the invocation branch in [invocation.md](./invocation.md).

## Buckets

Skills live in bucket folders under `skills/`:

- `engineering/`: daily code work
- `productivity/`: daily non-code workflow tools
- `misc/`: kept around but rarely used, not promoted
- `in-progress/`: beta, public on purpose, feedback wanted, not shipped in the plugin
- `deprecated/`: no longer used

## Promoted set

`engineering/` and `productivity/` are the **promoted** buckets. Every promoted skill must have a reference in the top-level `README.md` and an entry in `.claude-plugin/plugin.json`'s `skills` array (the Claude Code plugin ships exactly the promoted set). Skills in `misc/`, `in-progress/`, and `deprecated/` must not appear in either.

After touching either manifest, run `claude plugin validate . --strict`. Why a Claude plugin but not (yet) a Codex one lives in [adr/0002-ship-as-a-claude-code-plugin.md](./adr/0002-ship-as-a-claude-code-plugin.md).

## README entries

Each skill entry in the top-level `README.md` must link the skill name to its `SKILL.md`.

Each bucket folder has a `README.md` that lists every skill in the bucket with a one-line description, with the skill name linked to its `SKILL.md`. The promoted buckets' `README.md`s and the top-level `README.md` group entries into **User-invoked** and **Model-invoked** (see [invocation.md](./invocation.md)); non-promoted bucket `README.md`s (`misc/`, `in-progress/`) use a flat list.

## The router: ask-matt

[`ask-matt`](../skills/engineering/ask-matt/SKILL.md) is the router that maps every user-reachable skill and how they relate. Whenever you add, rename, remove, or change how a user-reachable skill fits the flows, re-read its `SKILL.md` and update it so the map stays accurate: a new skill it never mentions, or a stale one it still routes to, is a router that lies.

## Linking installed skills

To (re)link every skill outside `deprecated/` and `misc/` into the local harness skill directories (`~/.claude/skills`, `~/.agents/skills`), run `scripts/link-skills.sh`. Each entry is a symlink into this repo, so a `git pull` keeps installed skills current; re-run the script after adding, removing, or renaming a skill.

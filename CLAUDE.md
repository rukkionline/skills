This file is a pointer index: reach the material behind each pointer only when its branch fires.

**Skill lifecycle** (add, rename, remove, or reorganise a skill, or change how one fits the flows): keep README.md, each bucket README.md, `.claude-plugin/plugin.json`, the `ask-matt` router, and `scripts/link-skills.sh` in sync. See `.agents/skill-lifecycle.md`.

**Install wording** (writing an install command in a README, changeset, or docs page): copy it verbatim from `.agents/install-block.md`, never paraphrase.

**Docs pages** (adding, renaming, or changing a promoted `engineering/` or `productivity/` skill): create or re-sync its page per `.agents/writing-docs.md`.

**Invocation** (setting a skill's frontmatter or `agents/openai.yaml`): decide user- vs model-invoked per `.agents/invocation.md`.

**Prose** (writing any SKILL.md, docs page, README, CHANGELOG, ADR, changeset, or code comment): follow `CODING_STANDARDS.md`.

**Triage** (labelling or judging an issue): use the canonical labels in `docs/agents/triage-labels.md`.

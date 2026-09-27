# UnitEd Resources — the system

One line: research decides the categories, the library fills them, and the
app walks each teacher through one small step at a time.

## Two readers

1. **The UnitEd web app** reads this repo over the GitHub API. It queries
   frontmatter — it never slurps bodies. A node's title is the file's first
   `# ` heading; graph edges come from wikilinks (double square brackets
   around an exact title).
2. **Agents and humans** add and organize content. Read top-down: this file →
   the folder's `CONTEXT.md` → the file itself. Load only what the task needs.

## The query protocol

- Every content file carries single-line YAML frontmatter: `type`,
  `category`, `tags`, `status` (plus `url` for external content). The schema
  lives in `20-resources/CONTEXT.md`.
- Frontmatter is the filter surface; bodies are read only when a resource is
  served — and provider-card bodies (`20-resources/30_providers/`) are read
  at step-time because they name which small part to fetch live.
- `_templates/` is excluded from scans — its files carry frontmatter but are
  stamps, not content.
- Valid categories are exactly the seven defined in
  `10-logics/20_content-framework/` — `1.1` through `3.2`. Nothing else is a
  category.
- Matching a teacher to their next step follows `10-logics/30_matching/`.

## The flows

| Flow | Path |
|---|---|
| New teacher → first step | app asks the profile questions → Jev evaluates the answers → one category → one resource from `20-resources/` |
| Teacher finishes a step → next step | `10-logics/30_matching/03_progression-rules.md` |
| New material arrives | dropped in `00-inbox/` → filed per `00-inbox/CONTEXT.md` |
| Big provider content | never mirrored — fetched live in small parts per `20-resources/30_providers/CONTEXT.md` |

Factory (stable): `_templates/` and `10-logics/`. Product (grows):
`20-resources/` and `00-inbox/`.

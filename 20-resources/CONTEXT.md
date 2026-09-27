# 20-resources — the library the app serves from

One job: hold the actual resources — ours, links, and big providers.

## Layout

| Folder | Holds |
|---|---|
| `10_native/` | UnitEd's own resources, always markdown |
| `20_links/` | third-party resources: one URL + what it is |
| `30_providers/` | big providers served in small parts, fetched live |

## The schema — every file, single-line frontmatter

```yaml
---
type: native | link | provider | logic
category: 1.1 | 1.2 | 1.3 | 2.1 | 2.2 | 3.1 | 3.2 | none
tags: [kebab-case, inline-list]
status: approved | draft
url: https://...        # link and provider files only
source: "Doc Title"     # logics files only — the research the text came from
---
```

The app parses frontmatter line by line — keep every field on one line.
`category` values are strings (`1.1` the code, not the number): consumers
must not YAML-coerce them.

## Rules

- `status: draft` is never served to teachers.
- The first `# ` heading is the title and the wikilink anchor. Rename a
  title and every wikilink to it breaks — rename the links in the same
  change.
- Body shape: `# Title`, one summary paragraph, then the content.
- Link with wikilinks (double square brackets around the target's exact
  title) wherever a natural connection exists — the links draw the graph the
  app renders.
- One resource per file. Small files beat crowded ones: split, don't grow.
- New files start as copies of `_templates/`, never blank pages.

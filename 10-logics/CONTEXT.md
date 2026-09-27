# 10-logics — why the library is shaped this way

One job: hold the research and rules that decide what a teacher learns next.

## Layout

| Folder | Holds | Text status |
|---|---|---|
| `10_learners/` | who UnitEd teaches | final research — verbatim |
| `20_content-framework/` | the seven content categories | final research — verbatim |
| `30_matching/` | how a teacher's profile picks the next step | authored operating rules |

## Rules

- The one rule (root `CLAUDE.md`) applies to both research folders.
- `30_matching/` is the only authored section. It implements the research;
  where they disagree, the research wins and the rules change.
- The categories defined here are the only valid values of `category:` in
  frontmatter across the repo.

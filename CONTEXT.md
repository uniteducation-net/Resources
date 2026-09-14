# Resources — Agent Contract

This repo is the curated, public resource library for UnitEd workspaces.
Humans browse `README.md`; this file is the contract for agents reading or
adding content.

## What belongs here

- Classroom-ready teaching resources: templates, guides, routines, rubrics.
- Every resource is **reviewed and approved** before it lands. No drafts,
  no unvetted external dumps.

## Layout

```
CONTEXT.md          this contract
README.md           human index (one wikilink bullet per resource)
resources/          one markdown file per resource
```

## Resource file schema

Every file in `resources/` starts with YAML frontmatter:

```yaml
---
type: template | guide | rubric | routine
subject: any            # or e.g. biology, mathematics
gradeLevels: [all]      # or e.g. [6-8, 9-12]
tags: [lesson-planning] # lowercase, hyphenated
status: approved        # required; anything else is not served
---
```

After the frontmatter: a `# Title` heading, a one-paragraph summary, then
the resource itself in plain, warm markdown.

## Wikilinks

Related resources link to each other with `[[Exact Resource Title]]` — the
title of the target resource as written in its `# Title` heading. Wikilinks
are how agents and teachers discover connected material; every resource
should link at least one other when a natural connection exists.

## Rules for agents

1. Read this file first. The frontmatter is the queryable surface — match
   teachers to resources by `subject`, `gradeLevels`, and `tags`, never by
   slurping full bodies.
2. Only `status: approved` resources exist here by definition; if a file
   lacks frontmatter or has another status, ignore it.
3. Never restructure, rename, or reformat existing resources.
4. New resources follow the schema above and add their bullet to `README.md`.

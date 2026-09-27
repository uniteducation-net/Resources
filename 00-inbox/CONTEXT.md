# 00-inbox — everything uncategorized lands here

One job: hold drops until they are filed into the structure.

## Inputs

- Working (this run): any file dropped here, any format.
- Reference (every run): `../20-resources/CONTEXT.md` — the schema.
- Reference (every run): `../10-logics/CONTEXT.md` — the logics map.

Do NOT load: whole subtrees. Read only the contracts and the drop.

## Process

1. Read the drop. Decide what it is: a native resource, an external link, a
   provider, or a logic.
2. If a home exists, move it: stamp the file from the matching
   `../_templates/` template, fill the frontmatter, link its neighbors with
   wikilinks on their exact titles.
3. If no home exists, do not force one. Propose the new folder or structure
   to a human and wait for approval before creating it.
4. Remove the drop from this folder only after the filed copy verifies.

## Outputs

- A filed file in `10-logics/` or `20-resources/`, linked into the graph.

## Human check

Confirm the filed copy kept the drop's content intact, and approve any
proposed new structure before it is created.

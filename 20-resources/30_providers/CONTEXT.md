# 30_providers — big sources served in small parts

One job: hold provider cards for sources too big to mirror. We take one
small part at a time, fetched from their site in real time, and serve only
that part as a step.

## The runtime-fetch contract

- A provider card never holds the provider's content. It holds: the URL,
  what the provider is, and which small parts are worth serving.
- When a step points at a provider, the app fetches the named page live and
  extracts only the named part. Nothing is mirrored into this repo.
- If the fetch fails, the step degrades to a link-out with the description
  from the card.
- The provider's `url:` is always shown as the source. Respect each
  provider's terms and attribution.

## Rules

- Stamp from `../../_templates/provider-card.md`.
- `category:` marks which teaching category the provider's useful parts
  serve; `none` for research sources.

## Adding a provider card

Inputs:

- Working: the provider's URL and the pages worth serving.
- Reference (every run): this file's runtime-fetch contract.

Process:

1. Verify every named part loads at its URL today.
2. Write the card: who they are, what we take (named precisely), when we
   suggest it.
3. Link the card to the logics or categories it serves.

Outputs: one card per provider, in this folder.

Human check: open each named URL once and confirm the named part is really
there — the runtime fetch depends on it.

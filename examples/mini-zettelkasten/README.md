# Mini Zettelkasten — a tiny working example

This folder is a complete, functioning Zettelkasten with **8 notes**, produced by following the `zettelkasten-organizer` skill. It exists to show what the method looks like in practice — not as theory, but as a small network you can explore in two minutes.

**Best way to explore it:** open this folder as a vault in Obsidian (or any wikilink-aware markdown reader) and follow the links. The graph view shows exactly what the method is about.

## The scenario

Someone heard about Luhmann's slip-box, read Sönke Ahrens' *How to Take Smart Notes*, and started building their Zettelkasten around the topic of **writing and thinking**. You are looking at their system one week in.

## What's here (the pipeline, end to end)

| Folder | Contents | What it demonstrates |
|---|---|---|
| `0 Inbox/` | 1 fleeting note | Raw capture, not yet processed — no polish, no links |
| `1 Literature/` | 1 literature note | One source, ideas paraphrased in the reader's own words, full reference |
| `2 Permanent/` | 3 permanent notes | Atomic notes: statement titles, full sentences, links with stated reasons |
| `3 Structure/` | 1 MOC + root index | Annotated maps into the cluster; the single entry point to the system |
| `4 Archive/` | 1 archived fleeting note | Nothing is deleted — processed notes rest here, marked with where they went |

## The network

Every permanent note links to at least one other note, and **every link carries a one-line reason** — that reason is what turns a pile of markdown files into a thinking tool.

- `202607281709` **Writing externalizes thought** → links to the other two permanent notes + the source
- `202607281815` **Emergent structure beats imposed taxonomy** → links to `202607281709` + the source
- `202607281902` **Notes are conversations with a future self** → links to `202607281709` + the source
- The literature note points to all three permanent notes it was distilled into
- The MOC and the root index tie the cluster together

## Conventions shown

- **IDs:** `YYYYMMDDHHMM` timestamp prefix in the filename *and* the frontmatter
- **Statement titles** for permanent notes ("Writing externalizes thought", never "Writing")
- **Topic titles** for structure notes (their job is orientation, not claims)
- **Frontmatter:** `id`, `type`, `created`, `tags`, `source`
- **The archived fleeting note** records what it was distilled into — the audit trail that makes people brave enough to process aggressively

This exact structure (folders + wikilinks + timestamp IDs) is the *plain markdown / Obsidian* expression of the method. The same network in Notion, Logseq, Craft, or on paper would change only its syntax — see `references/tool-adaptations.md` in the skill.

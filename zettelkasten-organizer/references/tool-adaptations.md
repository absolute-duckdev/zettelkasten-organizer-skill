# Tool Adaptations

How to express the four Zettelkasten primitives — containers, links, IDs, tags — in common note-taking tools. Use this after Step 0 (discover the tool and access). The method never changes; only syntax does.

**Access model reminder:** if you can read/write the notes directly, work in place. If not, deliver standard markdown files (every tool below reads or imports them) plus brief import instructions. No tool-specific workarounds beyond that.

## Quick mapping table

| Tool | Containers | Links | Unique ID | Tags |
|---|---|---|---|---|
| **Obsidian** | Folders (or flat + property) | `[[wikilinks]]`, backlinks native | Filename prefix or `uid:` in frontmatter | `#tags` or frontmatter |
| **Logseq** | Pages + namespaces (or journals) | `[[wikilinks]]`, backlinks native | Page property `id::` or title prefix | `#tags` or page properties |
| **Notion** | One database, `Type` property | Relations + backlinks | `ID` property (or title prefix) | Multi-select property |
| **Craft** | Folders/documents | Document links + backlinks | Title prefix (`202607281709 Title`) | Tags feature |
| **Plain markdown** | Folders | Relative links or `[[wikilinks]]` | Filename prefix + frontmatter `id:` | Frontmatter |

## Obsidian

- **Containers:** folders work (`0 Inbox/`, `1 Bib/`, …), but Obsidian culture leans flat: one folder, note type as a frontmatter `type:` property or `#type/permanent` tag, organization via links and MOCs. Offer both layouts (SKILL.md, Mode 1).
- **Links:** `[[Note title]]` — Obsidian resolves by name, so links survive without IDs. Backlinks panel shows inbound connections automatically; still write the "why" line next to each link in the body.
- **IDs:** optional here. If wanted, use filename prefix `202607281709 Title.md` or `uid: 202607281709` in frontmatter. Do not insist — Obsidian's name-based linking makes IDs redundant for many users.
- **Tags:** native `#tag`; keep to the few stable ones.
- **Working directly:** an Obsidian vault is just a folder of markdown — read/write files in place.

## Logseq

- **Containers:** Logseq is an outliner — everything is a page. Use pages or namespaces (`Permanent/Title`) for note types; the **journal is a natural inbox** — fleeting notes land on the day's page and get processed into pages.
- **Links:** `[[Page name]]` with native backlinks. Blocks can also be referenced (`((block-id))`) — useful for linking a specific claim inside a long page, though permanent notes should be pages, not blocks.
- **IDs:** page property `id:: 202607281709`, or title prefix. Often skipped; name-based linking suffices.
- **Tags:** `#tag` or page properties (`type:: permanent`).
- **Working directly:** a Logseq graph is a folder of markdown/org files — read/write in place, respecting its page conventions.

## Notion

- **Containers:** one database (e.g., "Zettelkasten") with a `Type` select property (Fleeting / Bib / Permanent / Structure / Project). Filtered views play the role of folders: an "Inbox" view (Type = Fleeting), a "Permanent" view, etc. Archive is a lifecycle view or location, not a note type.
- **Links:** a `Related notes` relation property on the database (self-referential), plus inline `[[mentions]]` in page bodies. Backlinks appear automatically on each page. The "why" line goes in the body next to the mention, or as a relation description.
- **IDs:** an `ID` property (text or created-time). Title prefix also works but clutters Notion's relation pickers — prefer the property.
- **Tags:** a multi-select property; keep the options list short and governed.
- **Delivering content:** markdown imports cleanly (each file → a page; then set `Type` and relations). When delivering artifacts, include a one-page "Notion setup" note: create database, add properties, import, set relations.

## Craft

- **Containers:** folders (Inbox, Bib, Permanent, Structure, Projects, Archive) inside a space — Craft's document-per-note model fits permanent notes well.
- **Links:** native document links (`@` mention / slash command) with a backlinks section on every document. Write the "why" line in the body next to each link.
- **IDs:** title prefix (`202607281709 Writing externalizes thought`) — Craft has no custom properties, so the title carries the ID.
- **Tags:** Craft's tag feature; keep few and stable.
- **Delivering content:** markdown imports as documents; structure notes can use Craft's card/page styles for a visual index.

## Plain markdown files

- **Containers:** folders — the containerized layout maps one-to-one.
- **Links:** relative markdown links (`[Title](../2%20Permanent/202607281709-title.md)`) are portable but brittle to renames; `[[wikilinks]]` are not portable everywhere. Default: `[[wikilinks]]` if the user may adopt a wikilink-aware tool later (most do); relative links if portability to strict CommonMark matters. Ask in Step 0 if unclear.
- **IDs:** filename prefix + `id:` in YAML frontmatter.
- **Tags:** frontmatter `tags:` list.
- This is the fallback format for delivery when no direct access exists — it is also a first-class long-term home.

## Anything else

Ask three questions in Step 0 and build the mapping from the answers:

1. How does this tool group notes? (→ containers)
2. How does it point from one note to another? (→ links — and are backlinks automatic?)
3. Can a note carry a stable identifier? (→ IDs)

If a primitive truly doesn't exist (rare), the fallback order is: links > containers > IDs > tags. A Zettelkasten with only links is still a Zettelkasten; one with only folders is a filing cabinet.

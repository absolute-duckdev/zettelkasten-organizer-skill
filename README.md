# Zettelkasten Organizer

A portable skill that turns an AI agent into a Zettelkasten assistant: it sets up, organizes, and maintains a slip-box note system in **any** note-taking tool — Obsidian, Logseq, Notion, Craft, or plain markdown files.

The method is the one developed by sociologist **Niklas Luhmann** (roughly 90,000 cards, 70+ books) and popularized by **Sönke Ahrens** in *How to Take Smart Notes*. Its core insight: the value of a note system is not in collecting notes but in the network of connections between them. **Folders organize; links think.**

## What the skill does

Four modes of use:

| Mode | What it does |
|---|---|
| **Initial setup** | Builds the structure (Inbox → Bib → Permanent → Structure → Projects → Archive), adapted to your tool's syntax |
| **Process the inbox** | Triages fleeting notes: archive, file as bib, or distill into atomic permanent notes |
| **New permanent note** | Drafts one atomic note with you: statement title, your own words, links with stated reasons |
| **Audit & maintenance** | Finds orphaned notes, dense clusters needing a MOC, atomicity violations, inbox debt, bare links |

Safety is built in: the skill **never creates, moves, splits, or deletes a real note until it has presented a complete written plan and you have approved it.**

## The method in 30 seconds

- **Fleeting notes** — quick captures of ideas. Raw material, processed within days.
- **Bib notes** — what a source says, paraphrased in your own words, with the full reference. They are also called literature notes.
- **Permanent notes** — the heart of the system. One idea per note (atomic), titled with a **statement** ("Writing externalizes thought", not "Writing"), and densely **linked** — every link carrying a line that explains *why* the notes connect.
- **Structure notes** — maps of content (MOCs): annotated indexes that emerge when a cluster of notes grows enough to need a map.
- **Project notes** — drafts, tasks, and working material for a specific deliverable, kept outside the permanent Vault.

## Installation

The folder `zettelkasten-organizer/` is self-contained — no dependencies, no build step.

**Claude Code** — copy the skill folder into your skills directory:

```bash
git clone https://github.com/absolute-duckdev/zettelkasten-organizer-skill.git
cp -r zettelkasten-organizer-skill/zettelkasten-organizer ~/.claude/skills/
```

**Craft Agents** — copy `zettelkasten-organizer/` into your workspace's `skills/` folder.

**Other compatible agents** — place the `zettelkasten-organizer/` folder wherever your agent loads skills from.

## Usage

Once installed, just talk to your agent. Example triggers:

- "Set up a Zettelkasten for my notes"
- "Process my notes inbox"
- "Help me write a permanent note about this idea: …"
- "Find orphaned notes in my vault"
- "Audit my note system"
- "Organize my notes with links instead of folders"

The skill adapts to your tool: it asks (or infers) where your notes live, maps the four primitives — containers, links, unique IDs, tags — to your app's syntax, and confirms the mapping before touching anything.

## Repository structure

```
zettelkasten-organizer-skill/
├── README.md                          ← you are here
├── LICENSE                            ← MIT
├── zettelkasten-organizer/            ← the skill (this folder is what you install)
│   ├── SKILL.md                       ← skill definition: frontmatter + workflow
│   ├── icon.svg
│   └── references/
│       ├── zettelkasten-framework.md  ← theory: note types, atomicity, linking rules
│       ├── note-templates.md          ← templates for every note type
│       └── tool-adaptations.md        ← syntax per tool: Obsidian, Logseq, Notion, Craft, plain markdown
└── examples/
    └── mini-zettelkasten/             ← a tiny working Zettelkasten produced by the skill
```

## The mini example

[`examples/mini-zettelkasten/`](examples/mini-zettelkasten/) is a complete, tiny Zettelkasten — 8 notes showing the full pipeline: one unprocessed fleeting note in the inbox, one bib note, three atomic permanent notes linked to each other, a map of content, the root index, and one archived fleeting note. Open the folder in Obsidian (or any markdown reader) to follow the links.

## License

[MIT](LICENSE) © 2026 [absolute-duckdev](https://github.com/absolute-duckdev)

## Credits

- **Niklas Luhmann** — the original Zettelkasten method
- **Sönke Ahrens** — *How to Take Smart Notes* (2017), the modern formulation this skill follows

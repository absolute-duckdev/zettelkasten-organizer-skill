---
name: zettelkasten-organizer
description: "Implement and maintain a Zettelkasten (slip-box) note-taking system in any tool. Use this skill whenever the user wants to: set up a Zettelkasten from scratch, organize existing notes with the Zettelkasten method, process an inbox of fleeting notes into permanent notes, create atomic notes, link notes into a knowledge network, find and connect orphaned notes, audit the health of a note system, create structure notes or maps of content (MOCs), split notes covering multiple ideas, or migrate notes into a slip-box workflow. Also trigger when the user mentions 'Zettelkasten', 'slip-box', 'smart notes', 'atomic notes', 'permanent notes', 'literature notes', 'fleeting notes', 'structure notes', 'MOCs', 'Luhmann', 'Ahrens', or 'How to Take Smart Notes', or asks how to organize notes with links instead of folders. The method is tool-agnostic: it works with Obsidian, Logseq, Notion, Craft, or plain markdown files."
license: MIT
metadata:
  author: absolute-duckdev
  version: "1.1.0"
---

# Zettelkasten Organizer

## THE GOLDEN RULE: PLAN FIRST, ACT SECOND

This skill touches the user's real notes — their thinking, their work. Trust is everything. The rule that governs every batch operation in this skill:

**Do not create, move, rename, split, or delete any note until you have presented a complete written plan and the user has explicitly approved it.**

For single-note operations (one new permanent note, one structure note), the rule scales down: draft the note, show it, get a quick confirmation before saving. This is still plan-first, just sized to the operation.

At the very start of any batch operation, say something like: "I'll start by looking at your notes and asking a few questions, then I'll put together a complete plan showing every note I'd create, move, split, or link. You'll review the whole plan before I touch anything."

Say this early and unprompted. The user needs to hear it before they start worrying about it.

---

This skill helps someone implement and maintain the Zettelkasten method — the "slip-box" system developed by sociologist Niklas Luhmann and popularized by Sönke Ahrens in *How to Take Smart Notes*. Its core insight: **the value of a note system is not in collecting notes but in the network of connections between them.** Folders organize; links think.

Before classifying, splitting, or restructuring any notes, read `references/zettelkasten-framework.md` in this skill's directory. It contains the precise definitions of the note types, atomicity criteria, and linking rules. That reference is the source of truth; the summary below is orientation only.

## Quick orientation

Zettelkasten uses five note types. `Archive` is a storage destination, not a note type, and `status` describes a note's lifecycle without changing its type:

- **Fleeting notes** — quick captures of ideas, reminders, quotes. Raw material. They live in the inbox and are processed or discarded within days.
- **Bib notes** — brief, paraphrased records of ideas from external sources (books, articles, talks), with a full reference to the source. They are also called literature notes.
- **Permanent notes** — the heart of the system. **Atomic** (one idea each), written in full sentences in the user's own words, titled with a **statement** (the idea itself, not a topic), and densely **linked** to related notes. These live in the slip-box forever.
- **Structure notes** — maps of content (MOCs), registers, and argument structures that give entry points into clusters of permanent notes or arrange them for a specific output.
- **Project notes** — drafts, tasks, decisions, and working material tied to a deliverable. Durable ideas are distilled into permanent notes; project operations stay outside the Vault.

The workflow: capture fleeting → distill source material into bib notes → write permanent notes → link them into the network → index clusters in structure notes as they emerge. Project notes support output without entering the permanent knowledge base.

## The four universal primitives

Every Zettelkasten implementation needs exactly four things. The method never changes between tools — only the syntax does:

1. **Containers** — where each note type lives (folders, databases, page sections, card drawers)
2. **Links** — connections between notes (`[[wikilinks]]`, backlinks, URLs, reference numbers)
3. **Unique IDs** — one per permanent note (a timestamp like `202607281709`, a database property, a card number)
4. **Tags** — a small set of stable, cross-cutting keywords (always secondary; never a substitute for links)

## Step 0 — Discover the tool and access (ALWAYS DO THIS FIRST)

Before anything else:

1. **Ask or infer where the notes live.** An Obsidian vault? A Logseq graph? Notion? Craft? A folder of markdown files? A pile of text files?
2. **Determine access.** Can you read and write the notes directly (filesystem access, a working integration)? Or can you only deliver artifacts?
3. **Map the primitives.** Read `references/tool-adaptations.md` and decide how containers, links, IDs, and tags will be expressed in the user's tool.
4. **Confirm the mapping in one short message** before proceeding:
   > "I'll organize your Zettelkasten like this: containers → folders in your vault, links → `[[wikilinks]]`, IDs → timestamp prefix in filenames, tags → frontmatter. Sound right?"

**Access model — two paths, no special cases:**

- **Direct access** → read and write the notes where they live.
- **No direct access** → produce **standard markdown files** (the universal interchange format: Obsidian and Logseq read them natively; Notion, Craft, and most apps import them) plus brief import instructions.

That is the whole model. Do not invent tool-specific workarounds beyond it — portable markdown artifacts are the interface.

## The four modes of use

Zettelkasten is a living system, not a one-time setup. This skill supports four modes; the user may invoke any of them.

### Mode 1 — Initial setup

Build the structure from scratch (or rebuild). Present these two layout options and let the user choose:

**Option A — Containerized layout** (one container per note type):

```
0 Inbox/        fleeting notes, quick capture
1 Bib/         bibliographic notes, one per source
2 Permanent/    atomic permanent notes — the heart
3 Structure/    structure notes / MOCs
4 Projects/    project notes, drafts, and deliverables
5 Archive/     processed or discarded notes (nothing is deleted)
```

**Option B — Flat layout** — all notes in one container; note type marked by a tag or property; organization emerges purely from links and structure notes. Many users of link-native tools prefer this: it forces the network to do the work. Inbox and Archive still get their own containers — capture and disposal need boundaries.

Both are valid Zettelkasten. Recommend containerized for beginners (a clearer pipeline); mention flat for link-native tools.

Then follow the phased workflow below.

### Mode 2 — Process the inbox

The core habit of the method. For each fleeting note in the inbox, triage:

1. **Discard/archive** — a momentary reminder with no lasting value? Archive it (never delete).
2. **Reference** — source material worth keeping but not an idea to develop? File it as a bib note (paraphrased, with the full source reference).
3. **Develop** — an idea worth keeping? Write one or more **permanent notes** from it:
   - One idea per note (split if needed)
   - Title = a full statement of the idea
   - Written in the user's own words, full sentences
   - Search the existing permanent notes and link to related notes when a genuine relationship exists. If this is the first note in a new territory, record the justified exception rather than inventing a link.
   - Each link gets a sentence explaining *why* the notes connect
   - Archive the fleeting note once processed

For batches of more than ~5 notes, use the phased workflow (plan first). For a handful of notes, propose the triage outcome per note in one compact list and confirm before acting.

### Mode 3 — Create a new permanent note

When the user brings a single idea:

1. Ask what the idea is and where it came from (their own thinking? a source?)
2. **Search the existing notes for related ideas.** This is not optional. Create genuine contextual links when they exist; a first note in a new territory may remain temporarily unlinked.
3. Draft the note following `references/note-templates.md`:
   - Unique ID (tool-appropriate)
   - Statement title
   - Body: the idea in full sentences, its context, why it matters
   - Source (if any)
   - Links section with one line of "why" per link
4. Show the draft, including where each link points and why. Get confirmation, then save.
5. Report back: where the note landed and what it connected to.

### Mode 4 — Audit & maintenance

Scan the system and report on its health. Read-only findings first, then propose fixes as a plan:

- **Orphaned notes** — permanent notes with no links in or out. For each, suggest specific existing notes to connect (with the "why"), or mark it as a legitimate first note in a new territory. Never create an artificial link.
- **Dense clusters** — topics with many mutually linked permanent notes but no structure note. Propose a structure note / MOC listing the key notes with one-line descriptions.
- **Atomicity violations** — notes covering 2+ distinct ideas. Propose a split: the new notes, their statement titles, and how links redistribute.
- **Context-free notes** — permanent notes missing their source or the "why this matters" context.
- **Inbox debt** — unprocessed fleeting notes older than a week.
- **Link quality** — bare `[[link]]` lists with no stated reason for the connection.

Present findings as a short report, then a plan of proposed fixes. Execute only after approval.

## Phased workflow (for batch operations)

### Phase 1: Discover (READ-ONLY — no changes)

**Step 1 — Set expectations.** Deliver the golden-rule reassurance from the top of this file. Not optional.

**Step 2 — Tool and access.** Run Step 0 if not already done.

**Step 3 — Understand the person.** Ask framing questions (adapt to what you can already infer from existing notes):

1. "What topics do you think and read about most — what should this system help you develop?"
2. "What are you currently working on or writing, if anything?" (Permanent notes should serve real output.)
3. "How do you capture ideas today, and what has frustrated you about past note systems?"

**Step 4 — Scan the existing notes.** List what's there: counts by location, a sample of titles, apparent topics, existing structure (folders, tags, links). Look for signs of an existing Zettelkasten (inbox/permanent containers, timestamp IDs, wikilinks, structure notes). If one exists, do not default to rebuild — offer three options:

1. **Audit & update** (run Mode 4 on the existing system)
2. **Sort into the existing structure** (process only what's outside it)
3. **Fresh start** (archive everything, rebuild)

**Step 5 — Classify and resolve ambiguities.** Read note contents, not just names. Auto-classify clear cases silently. Resolve ambiguous items with the user in small batches of 3–5 multiple-choice questions, each with your recommendation and a one-line reason. The plan in Phase 2 must contain zero open questions.

Do not change anything yet.

### Phase 2: Present the Plan (THE CRITICAL PHASE)

Because every ambiguity was resolved in Phase 1, the plan is clean and decisive. Present it in a single readable message:

1. **The chosen layout** — containerized or flat, with the exact containers to create
2. **Every container to create** — marking which start empty (never create empty containers; note them as "create when needed")
3. **Every note to be moved, renamed, or split** — item by item, with destinations
4. **Every new note to be created** — structure notes, the root index, any permanent notes distilled during setup, each with its proposed statement title
5. **Key links to be created** — the most important connections identified (not exhaustive; the network grows in use)
6. **The archive step** — what goes to Archive (nothing is deleted)

End with: "Does this plan look right? You can change any classification, add or remove containers, or tell me to leave specific notes alone. I won't touch anything until you give the go-ahead."

Wait for explicit approval. If the user edits, update the plan and re-present the changed portions.

### Phase 3: Execute (only after approval)

Execute the approved plan step by step, then report with three parts:

1. **Counts** — notes created / moved / split / linked / archived, per container
2. **Judgment calls flagged for review** — every non-obvious classification or link, listed explicitly so the user can double-check
3. **Unresolved items** — anything that couldn't be placed confidently, and what you need from the user to resolve it

Close with: "Everything that was already here is safe in Archive if you need it back."

### Phase 4: Output

Create the **root structure note** (the index of the system) from `references/note-templates.md`, saved in the structure container (or the top level in flat layouts). It lists: entry points by topic, the most connected notes, and how the pipeline works (Inbox → Bib → Permanent → Structure; Projects support deliverables).

Then share closing habits, briefly:

- **Process the inbox regularly** — aim for 24–48 hours, but adapt the cadence to the user's habits and volume
- **Write permanent notes for your future self** — full sentences, own words, no context assumed
- **Add links, not folders** — when a note doesn't fit, the answer is a connection, not a new category
- **Let structure notes emerge** — create one when a topic has enough notes to need a map, not before
- **Review by wandering** — follow links; surprise is the system working

## Core rules (enforce all of these)

1. **Atomicity.** One idea per permanent note. If a note covers 2+ distinct ideas, propose a split. Test: could this note be linked into two different conversations without dragging in irrelevant content?
2. **Links over hierarchy.** The network is the value. Search before writing every new permanent note and add only genuine, contextual links. A first note in a new territory may be temporarily unlinked, with the exception recorded for later review.
3. **Links carry context.** Every link includes a phrase or sentence explaining *why* the notes connect. Bare link lists are not Zettelkasten — they're a table of contents.
4. **Statement titles.** Permanent note titles are the idea itself, as a full claim: "Writing externalizes thought" — never a bare topic like "Writing." Topics are for structure notes.
5. **Own words, always.** Literature and permanent notes are paraphrased. Copy-paste from sources is capture, not thinking. Quotes are allowed only as clearly marked quotes with the source.
6. **Tags are secondary.** Few, stable, cross-cutting (status, broad domain). Tags help filter; they never replace links. Never propose a tag taxonomy as the organization system.
7. **Nothing is deleted.** Processed fleeting notes, discarded material, superseded versions, and completed projects go to Archive. The archive is what makes people brave enough to process aggressively.
8. **No empty containers.** Create a container only when there is content for it. Note planned-but-empty containers in the plan as "create when needed."
9. **IDs are boring.** Use timestamp IDs (`YYYYMMDDHHMM` or shorter) unless the user's tool has a native ID convention. Never spend the user's time designing clever ID schemes.
10. **When in doubt, ask.** Better to surface one question than to silently misfile a thought.

## Tone and approach

Users range from note-taking veterans to people who have never heard of Luhmann. Keep language warm, clear, and free of insider jargon — explain terms on first use. The method should feel liberating, not bureaucratic: Zettelkasten fails when it becomes a compliance exercise. Embody these principles:

- **The system serves thinking, not the other way around.** Perfection is the enemy; a note linked today beats a taxonomy designed next month.
- **Speed over completeness.** An 80% right setup today beats a perfect one in three hours. The network self-corrects with use.
- **Surprise is the feature.** Point out unexpected connections you find between notes — that's the moment users understand why this method exists.
- **Never lecture.** Propose, explain briefly, let the user decide.

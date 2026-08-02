# Zettelkasten Framework Reference

This is the source of truth for classification, linking, and splitting decisions made by the `zettelkasten-organizer` skill. Read it before doing any batch work on real notes.

## Origins

- **Niklas Luhmann** (1927–1998), German sociologist, published 70+ books and hundreds of articles. He credited his productivity to his *Zettelkasten* ("slip-box"): roughly 90,000 hand-written index cards, each holding one idea, each numbered and cross-referenced to other cards. He described the slip-box as a communication partner that surprised him — a system that produced ideas he didn't know he had.
- **Sönke Ahrens**, *How to Take Smart Notes* (2017), translated Luhmann's practice into a modern, tool-independent method. This reference follows Ahrens' formulation.

## The core insight

A note's value is determined by its **connections**, not its content alone. An isolated fact is trivia; a fact linked to twenty other notes is a thinking tool. The practical consequences:

1. **Links beat folders.** A folder answers "where does this go?" — a link answers "what does this relate to?" The second question is the one thinking asks.
2. **Emergence beats classification.** The system's job is not to file ideas into a pre-designed taxonomy but to let unexpected clusters surface. Surprise is the signal that the system is working.
3. **Writing is thinking.** A permanent note is not a record of a thought already finished — the act of writing it, in full sentences, in your own words, *is* the thinking.

## The five note types — precise definitions

### Fleeting notes

- **Purpose:** capture, not keep. They exist only to not lose an idea before it can be properly considered.
- **Lifespan:** days. Processed within a week at most.
- **Content:** anything — a thought in the shower, a quote, a reminder, an objection.
- **Location:** the inbox.
- **Test:** if a fleeting note is still unprocessed after a week, it's inbox debt.

### Bib notes

- **Purpose:** record what a *source* says, in your own words, so ideas can enter the network with their origin attached. These are also called literature notes.
- **Type value:** use `type: bib` in portable metadata.
- **Cardinality:** one per source (or per chapter for dense books).
- **Content:** only the ideas relevant to your thinking, paraphrased and ultra-brief; the full bibliographic reference; page or location references for specific ideas.
- **Not:** a summary of the whole source. Selectivity is the skill — you record what matters to *your* questions, not the author's table of contents.
- **Quotes:** allowed sparingly, always marked as quotes, always with a page reference. A literature note that is mostly quotes has not been digested.

### Permanent notes

- **Purpose:** the idea itself, developed for the long term. This is the slip-box proper.
- **Atomic:** exactly one idea per note (see criteria below).
- **Autonomous:** fully understandable on its own — written for a reader with no context: your future self in five years.
- **Title:** a **statement** — the claim the note makes (see below).
- **Body:** full sentences, your own words. The idea, the context in which it holds, why it matters, what it implies.
- **Source:** where the idea came from, if external (a link to the bib note, or a direct reference).
- **Links:** to related permanent notes, each with a stated reason.

### Structure notes (maps of content / MOCs)

- **Purpose:** entry points and maps for topics that have grown enough to need one.
- **Content:** annotated lists of links — each link accompanied by one line on what the note says or why it's listed. May include a short framing of the topic's key tensions or open questions.
- **Emergent:** created when a cluster forms, revised as the topic grows. Never created preemptively for an empty topic.
- **Not:** rigid tables of contents. Multiple structure notes can index overlapping sets; a permanent note can appear in several maps. The map is a view, not a container.

Structure notes include MOCs, small keyword registers, and argument structures. A MOC is a reusable map of an emerging cluster; a register offers a few curated entry points; an argument structure arranges notes for one project or output.

### Project notes

- **Purpose:** support a specific deliverable with drafts, tasks, decisions, research questions, and working outlines.
- **Location:** a project container, separate from the permanent Vault.
- **Boundary:** extract durable concepts into `type: permanent` notes, preserving the project as conceptual origin when useful. Do not move task status, deadlines, assignments, or other operational noise into the Vault.
- **Lifecycle:** completed or abandoned projects are archived, not deleted, unless the user explicitly requests deletion.

## Atomicity — the criteria

One note = one idea = one claim that could be true or false.

**Tests:**

1. **The drag test:** could this note be linked into a new conversation without dragging in irrelevant content? If linking it somewhere pulls along a second idea that doesn't belong there, split it.
2. **The "and" test:** does the title need "and" (or a comma list) to cover the content? Split.
3. **The length test:** is the body past roughly 300–500 words? Either it holds two ideas, or the idea isn't understood yet. Both are reasons to split or sharpen.

**How to split:**

1. Give each part its own statement title and ID.
2. Redistribute links deliberately — ask for each original link which part it truly belongs to.
3. Link the parts to each other (they were, after all, written together) with the reason stated.
4. The original note becomes a small hub linking the parts, or goes to Archive. Never leave a zombie note that duplicates its children.

## Linking rules

1. **Link on relationship, not keyword overlap.** The useful relationships are: *X explains Y*, *X contradicts Y*, *X is an example of Y*, *X generalizes Y*, *X raises the question that Y answers*, *X applies Y to a new domain*. "Both mention productivity" is not a relationship.
2. **Every link states its reason** — one line, written at link time. A link without a reason is invisible to your future self.
3. **Link to the most specific relevant note**, not to the nearest topic hub. Hubs are for browsing; specific links are for thinking.
4. **Mind both directions.** When linking A → B, check whether B should mention A. In tools with backlinks this happens automatically; in tools without, add the return link when it adds meaning.
5. **No artificial links.** A permanent note with no links may be the legitimate first note in a new territory. Record the exception as a status such as `draft` or `review`, and revisit it later. If the note is neither atomic nor useful on its own, keep it fleeting or archive it instead.

## Statement titles

- The title is the idea compressed into a claim: **"Deliberate practice requires immediate feedback"** ✅ — not **"Deliberate practice"** ❌.
- **Why:** a scan of titles is a scan of your own thinking. Topic titles are invisible arguments — they tell you where things are, not what you believe. Statement titles let you browse your positions, spot contradictions, and assemble outlines.
- **Diagnostic:** when a note resists compression into a statement, the idea isn't understood yet. That's information, not failure — sharpen the thinking before filing the note.
- Structure notes keep topic-style titles ("Learning", "Writing"), because their job is orientation, not claims.

## Tags

- **Few** (a dozen or fewer across the whole system), **stable**, **cross-cutting**.
- **Good uses:** status markers (`#draft`, `#review`, `#obsolete`), broad life/work domains (`#work`, `#personal`), note-type markers in flat layouts.
- **Bad uses:** topic tags duplicating what links already express. A `#productivity` tag on every productivity note adds nothing the structure note doesn't already do better.
- **The distinction:** tags answer "show me notes of this *kind*"; links answer "what *relates* to this note." The second question does the heavy lifting in Zettelkasten.

## Collection vs. network — the diagnostic

| Collection | Network |
|---|---|
| Notes sorted by topic | Notes linked by relationship |
| Retrievable if you remember where you filed them | Retrievable from many directions |
| Silent | Surprising |
| Value scales linearly with notes | Value scales with connections |

**Warning signs of collection-thinking:** deep folder hierarchies; elaborate tag taxonomies; notes with zero links; anxiety about "where do I file this?"; a perfect structure with nothing in it.

**The fix is never better filing — it's more and better links.**

## The pipeline: capture → output

```
fleeting note
   → (idea from a source? → bib note)
   → permanent note(s), atomic, statement-titled
   → linked into the network
   → indexed in a structure note (when the cluster forms)
   → written output assembles from the network
```

The final step is the point of the whole system: producing output (articles, essays, decisions, talks) becomes an act of *retrieval and assembly* from the network, not a blank-page exercise. When advising on maintenance, always connect habits back to this purpose — notes exist to be used, not to be admired.

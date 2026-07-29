# Note Templates

Generic markdown templates for every Zettelkasten note type. Adapt syntax per `tool-adaptations.md` (link format, ID placement, frontmatter vs. properties). The `[[wikilink]]` syntax shown here is the default; substitute the user's tool convention.

IDs below use the `YYYYMMDDHHMM` timestamp convention. Replace with the tool-appropriate ID agreed in Step 0.

---

## Permanent note

```markdown
---
id: 202607281709
type: permanent
created: 2026-07-28
tags: []
source: "[[202607281200 - Source title, if any]]"
---

# Writing externalizes thought

The act of putting an idea into full sentences forces a precision that
thinking alone never achieves: vague intuitions either survive being
written or reveal themselves as gaps. [Develop the idea: what it claims,
the context in which it holds, its implications.]

## Why it matters

[One short paragraph: why this idea earns a permanent place. What does it
change, enable, or contradict?]

## Links

- [[202603140930 - Related statement title]] — because this note gives the
  mechanism behind that claim.
- [[202511021845 - Another statement title]] — contradicts this one on the
  role of memory; worth resolving.
```

**Checklist before saving:**

- [ ] Exactly one idea (passes the drag test and the "and" test)
- [ ] Title is a full statement, not a topic
- [ ] Body in the user's own words, full sentences, understandable alone
- [ ] Source recorded (or marked as own thinking)
- [ ] At least one link with a stated reason — or a justified exception

---

## Literature note

```markdown
---
id: 202607281200
type: literature
created: 2026-07-28
tags: []
source: "Ahrens, S. (2017). How to Take Smart Notes. CreateSpace."
---

# Ahrens — How to Take Smart Notes (2017)

[Only the ideas relevant to the user's thinking, paraphrased and brief.
Not a summary of the whole book.]

- Writing notes is not the byproduct of reading — it is the actual work of
  understanding. (ch. 1)
- The slip-box imposes no order upfront; structure emerges bottom-up from
  clusters of notes. (ch. 2)
- Permanent notes must be written as if for publication: full sentences,
  no assumed context. (ch. 3)

> "Nobody ever starts from scratch." (p. 42) [quotes sparingly, marked,
> with page]

## Distilled into permanent notes

- [[202607281709 - Writing externalizes thought]]
- [[...]] — add as permanent notes are written from this source
```

---

## Fleeting note

```markdown
---
id: 202607281730
type: fleeting
created: 2026-07-28
---

Idea while walking: maybe the reason my old notes died is that I filed
them by topic instead of by what they related to. Check against the
collection-vs-network distinction when processing.
```

No ceremony. Fleeting notes are raw capture — no links, no polish required. They are processed within days and then archived.

---

## Structure note (map of content)

```markdown
---
id: 202607281800
type: structure
created: 2026-07-28
tags: []
---

# Writing & Thinking

Entry point into the notes on how writing relates to thinking. The
cluster's open question: does the quality of writing *cause* the quality
of thought, or merely reveal it?

## Core claims

- [[202607281709 - Writing externalizes thought]] — writing forces
  precision that pure thinking skips
- [[202602011015 - Notes are conversations with a future self]] — notes
  fail when written only for the present moment
- [[202604221130 - Emergent structure beats imposed taxonomy]] — bottom-up
  order is more robust than top-down filing

## Tensions & open questions

- [[202511021845 - Memory strengthens through retrieval, not storage]] —
  sits awkwardly with heavy reliance on external notes; unresolved.

## Sources behind this cluster

- [[202607281200 - Ahrens — How to Take Smart Notes (2017)]]
```

Structure notes keep **topic titles** (their job is orientation, not claims) and every listed link carries one line of annotation.

---

## Root index

The single entry point to the whole system, created at setup and maintained over time.

```markdown
---
id: 202607281700
type: structure
created: 2026-07-28
---

# Zettelkasten Index

## How this system works

Capture in **Inbox** → distill sources into **Literature** notes → write
**Permanent** notes (atomic, statement-titled, linked) → map clusters in
**Structure** notes → processed material rests in **Archive**.

## Entry points

- [[202607281800 - Writing & Thinking]] — how writing and thought shape
  each other
- [Add structure notes here as clusters emerge]

## Most connected notes

- [[202607281709 - Writing externalizes thought]] (7 links)
- [Keep short — this is a dashboard, not a census]

## Habits

- Process the inbox weekly
- Every permanent note links to at least one other
- Create structure notes only when a cluster needs a map
```

---

## Adaptation notes

- **Flat layouts:** drop the `type` values into a tag (`#type/permanent`) or property instead of relying on containers.
- **Tools without frontmatter:** move `id`, `type`, `created`, `source` into the tool's native properties, or into the filename (`202607281709 Writing externalizes thought.md`).
- **Paper:** replace `[[wikilinks]]` with card numbers ("see 202607281709") and keep the same sections.

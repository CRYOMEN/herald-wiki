---
name: lore-wiki-maintainer
description: >-
  Maintain a narrative / lore wiki (game or story worldbuilding built from
  Markdown files) with strict no-duplication discipline. Use this whenever the
  user is adding, editing, reorganizing, or deduplicating lore — character
  sheets, locations, factions, technology, events, relationships — or turning
  raw notes, voice transcripts, records, or idea dumps into canonical wiki
  files. Trigger for requests like "add this to the wiki", "update a
  character's page", "process the notes inbox", "where does this note belong",
  "is this already documented somewhere", "clean up / merge the lore", or "did
  I contradict canon" — even when the user never says the word "wiki". The
  rules are tool-agnostic so the same skill works in Claude, Codex, and other
  agents.
---

# Lore Wiki Maintainer

A lore wiki is a single source of truth for an invented world. Its value collapses the moment the same fact lives in two places, because the two copies drift and no reader can tell which is canon. So the whole job reduces to one discipline: **every fact lives in exactly one file, and everything else links to it.** Keep that true and the world stays consistent, edits stay local, and contributors can trust what they read.

These rules are **tool-agnostic** — written for any coding agent (Claude, Codex, Cursor, Gemini, and others) and for human contributors alike. They describe the *method*. The specifics of *this* wiki — which folders exist, which files are protected, what language canon is written in — are provided by the repository itself (see the root `AGENTS.md`, and `.wiki-config.md` if present). Read those first.

## Choose your workflow

- **Adding or changing a single fact** (a trait, a date, a location detail) → follow *Adding or editing a fact* below.
- **Processing a folder of raw notes, records, voice transcripts, or idea dumps** into the wiki → read `references/processing-records.md` and follow it. That workflow is distinct: raw-note folders get emptied when done, idea folders get preserved.
- **A judgment call about whether two passages are duplicates**, or how to safely merge them → read `references/deduplication.md`. It has the full rules and worked examples. Consult it whenever you are about to add content that might already exist, or about to delete a duplicate.

## Step 0 — Load the project config first

The method is universal; the project is specific. Before touching any file, learn four things about *this* wiki:

1. **Folder → topic map** — which folder owns which kind of fact.
2. **Protected files** — files you may never edit without asking first.
3. **Language** — the language canon is written in.
4. **Quirks** — any project-specific conventions (naming, templates, special folders).

Find this in the repository's `AGENTS.md` (a `Project Config` / structure / "files never to edit" section), a `.wiki-config.md` at the wiki root, or `CLAUDE.md`. If you find **no config**, do not guess. Discover the folder structure by listing the directories (`ls`, or a `**/` glob) and infer topics from folder names, then **ask the user** which files are protected and what language to write in before you make any change. A wrong guess about a protected file or the right folder is exactly the kind of mistake this method exists to prevent.

## The core principle: no information duplication

Each fact exists in one file; other files link to it. This is a structural rule, not a style preference — a duplicated fact is a wiki *error* even when reworded.

The traps that catch people:

- **Paraphrase counts.** Two passages that communicate the same fact in different words are still duplicates. One must become a link.
- **Partial restatement counts.** Don't repeat a shorter version of a fact defined in full elsewhere.
- **Category boundaries hold.** A file may *name and link* a fact from another category, but must not *explain* it. A character file says a character wields an ability and links to the technology file; it does not re-describe how the ability works.
- **Same words ≠ same fact.** Identical text serving a genuinely different purpose in two places is not duplication. Before merging, ask: does this serve the same purpose in both spots? If the purposes differ, leave both.

When these get subtle, read `references/deduplication.md` rather than guessing.

## Record only what you're given — don't invent canon

A lore wiki is only trustworthy if every fact in it came from the author, not from the agent filling gaps. Invented detail is dangerous precisely because it reads as canon: once written, no one can tell a synthesized mechanism, date, or motive from a real one, and it propagates into other files and future edits.

So add only the facts the user — or the source note you're processing — actually provided. Do not synthesize new detail to "complete" a file or flesh out a thin section, even when the addition would be plausible or fit the established style.

This bites hardest when you redirect a fact to its authoritative home. If a request would place a fact in the wrong category (e.g. "describe how this ability works, on the character's page"), the correct move is to hold the boundary and point to the authoritative file — not to compose a fuller write-up for that file to justify the redirect. If the user gave no new details for the authoritative file, leaving it unchanged (with the link intact) is a complete and correct result. When you believe a detail is genuinely missing, ask the user for it rather than supplying it yourself.

## Adding or editing a fact

1. **Find the authoritative file.** Use the folder→topic map. Among candidates, the authoritative file is the one that already holds the most about that topic. Determine this dynamically by listing files and searching (`grep`/`ripgrep`) — never from memory or a hardcoded list, because the file set changes over time.
2. **Search before you write.** Search the whole wiki for the key concepts first. This is how you avoid creating a duplicate you didn't know existed.
3. **Decide from what you found:**
   - *Already present* → do nothing.
   - *Partially present* → add only the missing detail to the authoritative file.
   - *Absent* → add it to the authoritative file.
   - *Contradicts canon* → **stop** (see *Contradictions*).
4. **Write it** in the project's language and narrative style (see *Writing style*), matching any template the target file follows — adding only the facts you were actually given (see *Record only what you're given*), never invented detail.
5. **Sweep for duplicates you just created or exposed.** After editing an authoritative file, search the wiki for the same topic and fix or relink anything that now restates it — proactively, without waiting to be asked. Before deleting any duplicate, confirm the surviving copy contains **all** details from the one you're removing; transfer unique details first. Deduplication must never lose information.
6. **Keep changes from cascading.** Adding one fact should mean editing one file. If you find yourself editing several, the structure is telling you to link instead of restate — e.g. instead of listing every member inside a location file, write "home to the local community" and link to that community's own page.
7. **Verify** (see *Verification before finishing*).

## Relationships and Events are special

**Relationships are bidirectional.** A relationship belongs to neither character alone — it lives in the relationship catalog, and both endpoints link to it. Don't document the same bond twice from two sides.

**Anything that changes over time during the story lives only in Events.** Event files are rich narrative documents: dialogue, emotion, atmosphere, character actions, scripts, and the consequences of the action. They serve writers, cutscene creators, and players, so include fine detail. Every other file references an event by link and never retells it. If you're unsure whether a fact is "static description" (belongs in Characters/Locations/etc.) or "something that happens" (belongs in Events), ask the user.

## Contradictions — stop, don't overwrite

When new information conflicts with existing canon — a different date, a changed name, a revised trait, a reordered sequence of events — **stop**. Show the user both versions plainly and ask which is correct. Never silently overwrite the old version or drop the new one. A silent overwrite can erase canon the user still considered true; surfacing the conflict is how the wiki stays trustworthy.

## Protected files

The project config lists files that are edit-locked. Never modify one without explicit user permission — ask first, every time, even for a change that looks trivially correct. These files are usually protected because they encode decisions the user wants to make personally.

## Writing style

- Write in the project's canon language (for most wikis, English), in every file and section, without exception — even when the request that triggered the edit was written in another language.
- Use **direct narrative statements**. State what is true. Do not explain canon with contrastive "not X, but Y" formulas — that phrasing smuggles in a second, negated fact and reads as hedging. State something false only when that negation is itself a canon fact (e.g. "the ritual leaves no scar" when the absence matters).
- Match the target file's existing structure and any template it follows.

## Verification before finishing

For **each** modified file, review the change critically with `git diff`:

1. **No information lost** — especially after a dedup or merge. If the diff removed a detail, confirm it survives elsewhere.
2. **No new duplication introduced** — the added text isn't restating something another file owns.
3. **Style intact** — narrative voice preserved, correct language, links valid and pointing at the authoritative file.

Fix what the review turns up, then finish. When you processed a raw-notes record, also confirm the record file was emptied (see `references/processing-records.md`).

## Working efficiently

The wiki can be large; spend effort on judgment, not on re-reading files you already understand.

- Use `grep`/`ripgrep` and globbing to locate content — don't read whole files to find a line.
- Use `sed` for bulk replacements and renames, and batch related edits into one pass instead of many single-file edits.
- Check a file exists before editing.
- Trust your shell operations — don't re-read a file just to confirm a change unless later logic depends on the new content.

## Reference files

- `references/deduplication.md` — full no-duplication rules with worked examples. Read when a duplication call is subtle or before deleting a duplicate.
- `references/processing-records.md` — step-by-step workflow for turning raw-note and idea folders into canonical files. Read when processing those folders.

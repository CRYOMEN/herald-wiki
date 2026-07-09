# Processing Raw Notes and Ideas into the Wiki

Some wikis keep temporary inbox folders — raw voice transcripts, brainstorm dumps, rough outlines, idea sketches — that need to be migrated into the canonical files. This is a different workflow from a single edit, and the two folder types have opposite end states. The project config names these folders; typical names are `Records/` (raw notes) and `Ideas/` (brainstorms), but confirm from the config.

| Folder type | Contents | End state |
|---|---|---|
| Raw notes (e.g. `Records/`) | Voice transcriptions, brainstorming dumps, rough outlines | **Emptied.** Every fact ends up in an authoritative file; the note file is left blank. |
| Ideas (e.g. `Ideas/`) | Loose concepts, story drafts, community suggestions | **Preserved.** Canon-compatible facts are extracted; the file itself stays intact as creative reference. |

## Finding the authoritative file

Never rely on a hardcoded list — the file set changes. For each topic:

1. List the relevant category folder to see what files exist.
2. Search the whole wiki (`grep`/`ripgrep`) for the topic's key terms.
3. The file already holding the most about that topic is authoritative.
4. If nothing covers it, ask the user before creating a new file.

## Raw-note files (the emptying workflow)

**Step 1 — Read and extract.** Read the whole note. Pull out concrete facts, lore, and character details. Ignore meta-commentary ("we should show this in the scene") and speculation — extract only concrete information.

**Step 2 — Search before adding.** For each fact, search the entire wiki first. Never add from memory; this is what prevents duplicates.

**Step 3 — Compare and decide.**

| Situation | Action |
|---|---|
| Already in the wiki | Do nothing |
| Partially present | Add only the missing details to the authoritative file |
| Absent | Add to the appropriate authoritative file |
| **Contradicts the wiki** | **STOP.** Show the user both versions and ask which is correct. Never overwrite or discard silently. |

**Step 4 — Edge cases.**
- *New file needed?* If no authoritative file exists for this kind of information, ask permission before creating one.
- *User rejects an addition?* Stop and wait for instruction.

**Step 5 — Empty the note.** Once every fact has been transferred, confirmed already present, or confirmed outdated, overwrite the note file with empty content. An emptied file is the signal that the note is fully processed.

### Definition of done (raw note)

- [ ] Every fact searched for in the wiki (grep)
- [ ] All genuinely new facts added to authoritative files
- [ ] All contradictions surfaced to the user and resolved
- [ ] Outdated / rejected information skipped
- [ ] Note file emptied

## Ideas files (the preserve workflow)

Ideas are mostly **inspiration, not canon** — treat them gently.

**Extract:** concrete facts about characters, events, locations, or technology that are consistent with the wiki, and new details that supplement existing authoritative files.

**Skip:**
- Story drafts and narratives (inspiration, not reference)
- Raw community/Patreon suggestions — don't add unless the user confirms
- Production notes (hiring, tools, resources, game-design musings)
- Anything that contradicts current canon — flag it, don't add it

**Outdated ideas:** older idea files may describe traits that were later revised. When an idea contradicts current canon, treat the wiki as authoritative and skip the stale content. Flag it to the user if you're unsure.

**End state:** unlike raw notes, idea files are **not emptied**. Leave them intact after extraction.

### Definition of done (idea file)

- [ ] All concrete, canon-compatible facts extracted and checked against the wiki
- [ ] New facts added to authoritative files
- [ ] Contradictions flagged to the user
- [ ] File left intact (not emptied)

## After processing

Run the standard verification from `SKILL.md` on every authoritative file you touched: `git diff`, confirm no information lost, no new duplication, narrative style and language intact.

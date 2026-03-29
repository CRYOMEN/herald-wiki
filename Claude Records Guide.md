# LLM Workflow: Processing Records and Ideas into Wiki

This document is for **LLMs only**. It describes the exact process for migrating content from `Records/` and `Ideas/` into authoritative wiki files.

For general wiki rules (no duplication, folder structure, linking), see [CONTRIBUTING.md](CONTRIBUTING.md).

---

## What Are These Folders?

| Folder | Contents | End State |
|---|---|---|
| `Records/` | Raw notes — voice transcriptions, brainstorming dumps, rough outlines | Every file is emptied. All information lives in authoritative wiki files. |
| `Ideas/` | Loose ideas, story drafts, concept sketches, Patreon brainstorms | Reviewed for new facts. Most content stays as-is (inspiration, not canon). |

---

## Finding the Authoritative File

Do not rely on a hardcoded list — the project files change over time. Determine the correct file dynamically:

1. Use `Glob` to list all files in the relevant folder (`Characters/`, `Events/`, `Locations/`, `Factions/`, `Technology/`).
2. Use `Grep` to search for the topic across the entire wiki.
3. The file that already contains the most information on that topic is the authoritative file.
4. If no file covers the topic, ask the user before creating a new one.

---

## Process for Each Record File

### Step 1 — Read and Extract

Read the full Record file. Identify all distinct facts, lore, and character details. Ignore meta-commentary ("we need to show this in the scene") and speculative phrasing — extract only concrete information.

### Step 2 — Grep Before Adding

Before adding anything, search the entire wiki for the key concepts. Never add based on memory or assumptions. This prevents duplicates.

```bash
grep -r "keyword" --include="*.md"
```

### Step 3 — Compare and Decide

For each piece of information from the Record:

| Situation | Action |
|---|---|
| Already exists in wiki | Do nothing |
| Partially exists | Add only the missing details to the authoritative file |
| Does not exist | Add to the appropriate authoritative file |
| **Contradicts existing wiki** | **STOP.** Show the user both versions. Ask which is correct. Do not overwrite or discard silently. |

### Step 4 — Handle Edge Cases

- **New file needed?** If no authoritative file exists for this type of information, ask the user for permission before creating one.
- **User rejects an addition?** Stop and wait for their instruction.

### Step 5 — Clear the Record

Once all information has been transferred, confirmed as already present, or confirmed as outdated — overwrite the Record file with empty content.

---

## Process for Ideas Files

Ideas files are different from Records. Most are **inspiration, not canon**.

### What to Extract

- Concrete facts about characters, events, locations, or technology that are consistent with the wiki
- New details that supplement existing authoritative files

### What to Skip

- Story drafts and narratives (they're for inspiration, not reference)
- Raw community suggestions (e.g., Patreon brainstorms) — don't add unless the user confirms
- Game design concepts and production notes (hiring, tools, resources)
- Information that contradicts current wiki (flag to user, don't add)

### Old/Outdated Files

Some Ideas files contain outdated descriptions (e.g., character traits that were later revised). When you spot contradictions with the current wiki, treat the wiki as authoritative and skip the outdated content. Flag it to the user if uncertain.

### End State for Ideas

Unlike Records, Ideas files are **not emptied** after review. They remain as creative reference material.

---

## Definition of Done

A Record file is complete when:
- [ ] All information searched for in the wiki (grep)
- [ ] All genuinely new information added to authoritative files
- [ ] All contradictions shown to the user and resolved
- [ ] All outdated/rejected information skipped
- [ ] Record file is emptied

An Ideas file is complete when:
- [ ] All concrete, canon-compatible facts extracted and checked against wiki
- [ ] New facts added to authoritative files
- [ ] Contradictions flagged to the user
- [ ] File left intact (not emptied)
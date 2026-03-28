# LLM Workflow: Processing Records into Wiki

This document is for **LLMs only**. It describes the exact process for migrating content from `Records/` into authoritative wiki files.

For general wiki rules (no duplication, folder structure, linking), see [CONTRIBUTING.md](CONTRIBUTING.md).

---

## What is Records/?

`Records/` contains raw, unformatted notes — voice transcriptions, brainstorming dumps, rough ideas. It is **temporary storage**. End state: every file in `Records/` is empty. All information lives in authoritative wiki files.

---

## Finding the authoritative file

Do not rely on a hardcoded list — the project files change over time. Instead, determine the correct authoritative file dynamically:

1. Use `Glob` to list all files in the relevant folder (`Characters/`, `Events/`, `Locations/`, `Factions/`, `Technology/`).
2. Use `Grep` to search for the topic across the entire wiki.
3. The file that already contains the most information on that topic is the authoritative file.
4. If no file covers the topic, ask the user before creating a new one.

---

## Process for Each Record File

**1. Read** the full Record file. Identify all distinct facts, lore, and character details. Ignore meta-commentary ("we need to show this in the scene") and speculative phrasing — extract only concrete information.

**2. Grep first.** Before adding anything, search the entire wiki for the key concepts. Never add based on memory alone. This prevents duplicates.

**3. Compare.** For each piece of information:
- Already exists in wiki → do nothing
- Partially exists → add only the missing details
- Does not exist → add to the appropriate authoritative file
- **Contradicts existing wiki** (e.g. a date, a name, an event sequence differs) → do NOT silently overwrite and do NOT discard. Stop, show the user both versions, and ask which is correct before proceeding. Example: "Record 28 says Alekandras arrived in 3000 BC, but Alekandras.md says 3200 BC — which is correct?"

**4. New file needed?** If no authoritative file exists for this type of information, ask the user for permission before creating one.

**5. Rejected addition.** If the user rejects an addition for any reason, stop and wait for their instruction on what to do next.

**7. Clear the Record.** Once all information has been transferred, confirmed as already present, or confirmed as outdated — overwrite the Record file with empty content.

---

## Definition of Done

A Record file is complete when:
- [ ] All information searched for in the wiki
- [ ] All genuinely new information added to authoritative files
- [ ] All outdated/rejected information skipped
- [ ] Record file is empty
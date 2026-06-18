# Contributing to Herald Wiki

Rules for maintaining the wiki. LLMs: also read [CLAUDE.md](CLAUDE.md).

---

## Folder Structure

| Folder | Contents |
|---|---|
| `Characters/` | Character sheets — identity, personality, backstory, relationships, abilities |
| `Locations/` | Settlements, cities, planets, geography |
| `Factions/` | Organizations and communities |
| `Technology/` | All technologies — human and alien |
| `Events/` | Full narrative events — dialogues, emotions, actions, scripts, cutscene details |
| `Relationships/` | Relationship catalogs with research and historical context |
| `Game/` | Game design — purpose, themes, gameplay systems, guides |
| `Records/` | **Temporary** — raw notes, get processed then cleared |
| `Ideas/` | **Temporary** — brainstorms, kept as creative reference |

---

## File Naming

Short Title Case names with spaces: `Alien Tech.md`, `Secret Organization.md`, `Jasmine's Kidnapping.md`. No underscores, no long names.

---

## Core Principle: No Information Duplication

Each fact exists in **exactly one file**. Other files **link** to it.

This is a hard structural rule, not a style preference. A duplicated fact is a wiki error even when it is rewritten in different words.

- **Between files:** don't copy info, link to the authoritative source
- **Within files:** don't restate the same fact in multiple sections
- **Paraphrase still counts as duplication:** if two passages communicate the same fact, one of them must be removed or reduced to a link
- **Partial restatement still counts:** don't repeat a shorter version of a fact that is already defined elsewhere
- **Category boundaries matter:** a file may name and link to a related fact, but must not explain facts that belong to another category
- **When removing a duplicate:** before deleting, check that the remaining instance contains ALL details from the one being removed. If the duplicate has any unique details — transfer them first, then delete. Deduplication must never cause information loss.
- **Same words ≠ same fact:** The same information used for a different purpose is NOT duplication. Before deduplicating, ask: does this text serve the same purpose in both places? If the purposes differ — it's not a duplicate, even if the words are identical.

### Duplication Examples

- If `Technology/` defines what an ability does, a `Characters/` file may say who uses it and link to the technology file, but must not repeat how the ability works.
- If `Locations/` defines how a place functions, other files may reference the place, but must not repeat its physical description or history.
- If a section already says a character's inner trigger, another section should refer to that trigger instead of restating it.

### Relationships

Relationships are **bidirectional** — they don't belong to one character.

### Events as Full Narratives

- Any fact that changes over time during gameplay or narrative must be described exclusively in `Events/`. If unsure, ask the director for clarification.
- Other files reference the event with a link, not a retelling
- Events are **rich narrative documents**: dialogues, emotions, atmosphere, character actions, scripts
- Events serve developers, cutscene creators, and players — include fine detail
- The event file documents both the action and its consequences

### Minimize Cascading Changes

Adding new content should require editing **one file**. If you're updating multiple files — the structure is wrong.

- Don't list specific entities in aggregate files — link to faction/community file instead
- Write "home to the [monster community](Factions/Monsters.md)" instead of listing each monster
- Character's connection to a location belongs in the character file, not the location file

---

## Writing Style

Write in direct narrative statements. Avoid explaining a point through contrastive formulas such as "not X, but Y" when a direct statement works better. This also applies to equivalent phrasing in any language used inside content files.

---

## Verification Before Committing

Foreach modified file Run `git diff` to compare the new version with the previous version. Then:
1. Critically review each change against the deduplication rules above. Verify that no information was lost and a narrative writing style maintained;
2. Make fixes and always keep narrative writing style.

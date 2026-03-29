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
| `Events/` | Narrative events and state changes |
| `Game/` | Game-facing content — gameplay, guides, quests |
| `Records/` | **Temporary** — raw notes, get processed then cleared |
| `Ideas/` | **Temporary** — brainstorms, kept as creative reference |

---

## File Naming

Short Title Case names with spaces: `Alien Tech.md`, `Secret Organization.md`, `Jasmine's Kidnapping.md`. No underscores, no long names.

---

## Core Principle: No Information Duplication

Each fact exists in **exactly one file**. Other files **link** to it.

- **Between files:** don't copy info, link to the authoritative source
- **Within files:** don't restate the same fact in multiple sections

### Minimize Cascading Changes

Adding new content should require editing **one file**. If you're updating multiple files — the structure is wrong.

- Don't list specific entities in aggregate files — link to faction/community file instead
- Write "home to the [monster community](Factions/Monsters.md)" instead of listing each monster
- Character's connection to a location belongs in the character file, not the location file

---

## Checklist Before Committing

- [ ] Information doesn't already exist elsewhere? (link, don't duplicate)
- [ ] No repetition within the same file?
- [ ] Information is in the correct file for its type?
- [ ] Temporal state change? → `Events/`
- [ ] Adding a new entity later won't force updates to this file?
# Contributing to Herald Wiki - Documentation Guidelines

## Purpose

This document provides guidelines for maintaining the Herald Wiki project structure. These rules are designed for:
- **Writers** creating narrative content
- **Developers** maintaining the project
- **Contributors** adding or modifying lore
- **Language models (LLMs)** assisting with documentation

The primary goal is to maintain **clean, non-redundant documentation** where information is stored in the most logical location and referenced (not duplicated) elsewhere.

## Folder Structure

| Folder | Contents |
|---|---|
| `Characters/` | Character sheets — static, intrinsic character properties contain identity, personality, backstory, relationships, and abilities |
| `Locations/` | Location files — settlements, cities, planets, geography and local infrastructure |
| `Factions/` | Organizations and communities (monster community, secret org, humanity) |
| `Technology/` | All technologies in the setting — human tech and alien tech, explain mechanisms and capabilities |
| `Events/` | Narrative events and state changes (battles, story moments, historical events, in-game events) |
| `Game/` | Game-facing content — gameplay info, player help, guides, quests |
| `Records/` | **Temporary** — raw, unformatted notes and dumps. Content here gets processed and moved to the appropriate folder, then deleted from Records |
| `Ideas/` | **Temporary** — loose ideas and brainstorms. Same lifecycle as Records |

## Core Principle: No Information Duplication

**Golden Rule:** Each piece of information should exist in **exactly one file**. Other files should **reference** that information via links, not duplicate it.

### Why This Matters/

- **Consistency:** Updates need to happen in only one place
- **Clarity:** Clear ownership of information prevents contradictions
- **Maintainability:** Easier to update and expand the project
- **Scalability:** As the project grows, duplication becomes exponentially harder to manage

---

## Common Mistakes to Avoid

### ❌ Mistake 1: "Let me add this detail here too, just in case"

**Problem:** Information gets duplicated "for convenience"

**Solution:** Trust the linking system. Add a clear link instead.

### ❌ Mistake 2: "This file needs context, so I'll copy that section"

**Problem:** Context becomes full duplication

**Solution:** Provide a one-sentence summary + link to the authoritative source

### ❌ Mistake 3: "I'll update this info here, but forget the other file"

**Problem:** Duplicated information gets out of sync

**Solution:** Information should only exist in one file, preventing this issue entirely

### ❌ Mistake 4: "The reader won't click links, so I'll include everything"

**Problem:** Files become bloated and unmaintainable

**Solution:** Herald Wiki is a **reference**, not a novel. Readers are expected to follow links for details.

---

## Checklist for Contributors

Before committing changes, ask yourself:

- [ ] Does this information already exist in another file?
- [ ] If yes, did I link to it instead of duplicating it?
- [ ] Is this information in the most logical file for its type?
- [ ] Does this information represent a temporal state change? (If yes, it belongs in an event file)
- [ ] Are my cross-references clear and accurate?
- [ ] Did I avoid including full specifications/narratives when a link would suffice?

---

## For Language Models (LLMs)

When assisting with Herald Wiki documentation:

1. **Always check existing files** before adding new information
2. **Ask the user** if you're unsure where information belongs
3. **Propose moving information** if you find it in the wrong file
4. **Create links** instead of duplicating content
5. **Flag duplications** when you encounter them

**Proactive behavior:**
- When reading a file, note if information seems misplaced
- Suggest reorganization when you spot duplication
- Propose creating new categorical files when needed (e.g., Monsters.md)

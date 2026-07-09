# No-Duplication Rules — Full Reference

The wiki's one hard structural rule: **each fact exists in exactly one file; every other file links to it.** A duplicated fact is an error even when it is reworded. This document is the detailed version of that rule, for when a call is subtle. Read it before deleting a duplicate or when you're unsure whether two passages collide.

## Why this matters

Duplicated facts drift. Someone updates one copy and not the other, and now the wiki contradicts itself and no reader can tell which version is canon. Linking instead of copying means a fact has a single home; update it once and every reference stays correct. Every rule below is downstream of that.

## What counts as duplication

- **Between files.** Don't copy information from one file into another. Link to the authoritative source instead.
- **Within a file.** Don't restate the same fact in multiple sections of the same file.
- **Paraphrase counts.** If two passages communicate the same fact, they are duplicates even if not one word matches. Reduce one to a link.
- **Partial restatement counts.** Don't repeat a shorter or summarized version of a fact that is defined in full elsewhere.
- **Category boundaries hold.** A file may *name and link* a related fact, but must not *explain* a fact that belongs to another category.

## What does NOT count as duplication

- **Same words, different purpose.** The same information used for a genuinely different purpose is not duplication. Before merging two identical-looking passages, ask: *does this text serve the same purpose in both places?* If the purposes differ, it is not a duplicate — leave both, even if the words match.

The test is purpose, not surface text. A ruler's title appearing as an identity fact on their character page, and that same title stated inside an event narrative as the reason a plot turn happens, are two different purposes; the event may state it in service of the scene.

## Worked examples

**Ability described in two places (duplication).**
Input: a technology page explains how a device's camouflage works. A character page for someone who uses that device also explains, in its own words, how the camouflage works.
Fix: on the character page, keep only that the character uses the camouflage and link to the technology page; delete the how-it-works explanation. The mechanism lives once, on the technology page.

**Location detail restated (duplication).**
Input: a location page describes a place's layout and dangers. An event page re-describes that same layout to set a scene.
Fix: the event links to the location page for the layout and spends its words on what *happens* there — the action, dialogue, and tension of the scene.

**Same fact, different purpose (NOT duplication).**
Input: A character's inner trigger is defined in their psychology section, and an event narrative shows that trigger firing during a scene.
Verdict: Not a duplicate. The character file *defines* the trigger; the event *dramatizes* it. Different purposes. The event may still link back to the character file rather than re-explaining the psychology.

## Removing a duplicate without losing information

Deduplication must never delete information. Before you remove a duplicated passage:

1. Identify which instance is authoritative (in the correct category folder, most complete).
2. Read the instance you intend to delete and list any detail it holds that the authoritative one does not.
3. **Transfer those unique details** into the authoritative file first.
4. Only then reduce the duplicate to a link.

If you delete first and check later, you will eventually erase a detail that existed nowhere else. Transfer, then delete — every time.

## Minimize cascading changes

If adding one piece of content forces you to edit several files, the structure is wrong — fix the structure instead of duplicating.

- Don't list specific entities inside aggregate files. Link to the faction or community file that owns the list.
  - Write `home to the local community` and link to that community's own page, instead of enumerating each member in the location file.
- A character's connection to a location belongs in the **character** file, not restated in the location file.
- Adding a new character, item, or event should mean creating or editing **one** authoritative file, with other files linking to it. If a change ripples across many files, step back and find the single home the fact should have had.

## Relationships are bidirectional

A relationship does not belong to one character. It lives in the relationship catalog (or the project's designated place for relationships), and both characters link to that entry. Documenting the same bond from each character's side is duplication — describe it once, link from both.

## Events own everything that changes over time

Any fact that changes over the course of the story or gameplay must be described exclusively in `Events/` (or the project's narrative-event folder). Static description — what a character *is*, what a place *looks like* — lives in its category file. What *happens* lives in Events, as a full narrative with dialogue, emotion, atmosphere, actions, and consequences. Other files link to the event; they never retell it. When a fact sits on the line between "static" and "changes over time," ask the user which it is.

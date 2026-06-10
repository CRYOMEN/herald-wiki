# CLAUDE.md

Instructions for Claude Code when working with this wiki. **This file is for Claude only.**

## Key References

- [CONTRIBUTING.md](CONTRIBUTING.md) — wiki rules for everyone (folder structure, naming, no-duplication). Read before editing any file.
- [Claude Records Guide.md](Claude Records Guide.md) — how to process `Records/` and `Ideas/` folders.

---

## Behavioral Rules

### Proactive Deduplication

When you edit an authoritative file, immediately grep the entire wiki for references to the same topic. If you find duplicated information in other files, propose fixing those too — don't wait for the user to notice.

```bash
# After editing Characters/Arturas.md, check what references him:
grep -r "Arturas" --include="*.md" -l
```

### Protected Files

- **Relationships/Alekandras Soulmates.md** — do not edit without explicit user permission. Always ask first.

### When Information Contradicts

If a Record, Idea, or any source contradicts existing wiki content (dates, names, event sequences), do NOT silently overwrite or discard. Stop, show both versions to the user, and ask which is correct.

### Adding New Information

Before adding any fact to the wiki:
1. Determine the authoritative file by topic type (see folder table in CONTRIBUTING.md)
2. Grep the wiki to check if the information already exists
3. If no authoritative file exists for this topic, ask the user before creating one

---

## Token Economy

Save tokens with these practices:

1. **Use bash/sed for bulk replacements** — not Edit tool one file at a time
2. **Use grep for searching** — don't Read entire files to find content
3. **Batch similar operations** — one sed pass, not multiple Edit calls
4. **Check file existence before editing** — `find` or `test` first
5. **Don't re-read files** — trust bash operations unless logic depends on verification
6. **Use Glob for file discovery** — find files by pattern, then batch with bash

### Typical Workflow: Rename File + Update References

```bash
# 1. Find all references
grep -r "Old Name" --include="*.md"
# 2. Batch update all at once
find . -name "*.md" -exec sed -i "s/Old Name/New Name/g" {} \;
# Done — no need to re-read files
```
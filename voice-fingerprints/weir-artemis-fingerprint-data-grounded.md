# Voice Fingerprint (Data-Grounded) — Andy Weir, *Artemis*

**Author:** Andy Weir
**Source file:** *Artemis* (`Artemis_-_Andy_Weir.epub`) — Chapter 1, first-person narrator **Jazz Bashara**
**Sample:** The complete Chapter 1 narrative, taken contiguously from the first line ("I bounded over the gray, dusty terrain toward the huge dome of Conrad Bubble.") and cut at the chapter boundary. Front matter (cover, title, copyright, TOC, dedication, map) and the Chapter-1 "Dear Kelvin" epistolary letters (`c001-sup`, a different register) are **excluded** so the numbers reflect Jazz's live narrative voice only.
**Sample size:** **5,708 words / 677 sentences / 210 paragraphs / 31,736 characters (~7,934 est. tokens).** Fits under the 6,000-word / 32,000-char cap; no truncation needed.
**Method:** Extracted from the EPUB spine (`container.xml` → `.opf` → `c001` XHTML), HTML stripped with BeautifulSoup, all metrics computed in Python over the sample. Figures below are measured, not estimated.

> **Scope / lineage note.** This profile is *Artemis*-specific and data-grounded; it complements the general `andy-weir-voice-fingerprint.md` (built from *The Martian* and *Project Hail Mary*). Jazz runs on the **same wisecracking-competent first-person engine** as Watney and Grace, but the data shows she is the **youngest, snarkiest, and most profane** of the three: higher profanity and slang, more combative banter, and — unlike *The Martian*'s log frame — she narrates in **immediate scene**, with the retrospective letter device parked in separate interludes.

---

## Quantitative summary

| Metric | Value |
|---|---|
| Words / sentences / paragraphs | 5,708 / 677 / 210 |
| Characters (~est. tokens) | 31,736 (~7,934) |
| Mean sentence length | **8.4 words** (median **7**) |
| Sentence-length std dev / longest | 4.95 / **31 words** (only 1 sentence ≥30w) |
| Sentences ≤3 words / ≤6 words | 97 (14.3%) / 280 (**41.4%**) |
| One-word sentences (≤2 words) | 19 (55) |
| Mean paragraph | 27.2 words / 3.2 sentences (median 21 / 3); longest 97w |
| Single-sentence paragraphs | 32 (15.2%) |
| Dialogue paragraphs | **129 (61.4%)** |
| Words inside quotation marks | 1,564 (**27.4%**); 171 quoted segments |
| Dialogue tags (~50 total) | **said 33 (66%)**, asked 3, replied 0, other ~14 |
| Untagged dialogue paragraphs | **82 / 129 (64%)** |
| Em dashes / parenthetical pairs | 23 / 9 |
| Ellipses / exclamation marks | 10 / 23 |
| Semicolons / colons / question marks | **1** / 12 / **49** |
| Quantitative references | **135** (11 digit tokens + 89 spelled-out + 35 units) |
| Contractions | 203 (**35.6 / 1,000 words**) |
| First-person pronoun tokens | 316 (~55 / 1,000 words) |
| Filler words | just 28, really 6, very 2, probably 2, actually 1 |
| Profanity | **34 tokens (5.96 / 1,000 words)**: shit 12, hell 8, ass 5, fuck 2, damn 2 |
| Top content words | said 35, Trond 23, Jin 23, Artemis 21, time 17, right 15, way 15, box 15, Bob 13, Conrad 12, airlock 12, suit 12, moon 12, shit 12, EVA 11, Aldrin 11 |

---

## 1. Sentence rhythm and length

- **Short and punchy is the baseline, quantified.** Mean sentence length is **8.4 words** (median **7**); **41.4%** of sentences are ≤6 words and **14.3%** are ≤3 words. The chapter contains **19 one-word sentences** (55 at ≤2 words).
- **The long sentence is essentially banned.** The longest sentence in 677 is **31 words**, and only **one** sentence reaches 30+. A std dev of **4.95** around a mean of 8.4 captures the tight/loose alternation — wide swing, but always resolving back to a short center rather than building periodic sentences.
- **Fragments do real work** — clipped technical calls ("*Metal fatigue.*") and stripped competence lines ("*I know metal.*", 3 words) land as beats. This is the "fragment-for-effect, cap-the-key-line-clean" pattern from the general Weir profile, now measured.

## 2. Vocabulary register

- **Plain, contemporary, spoken.** **203 contractions** (35.6 per 1,000 words) and 316 first-person pronouns give a heavily conversational, off-the-cuff feel. Casual filler is present but light — "*just*" 28×, "*really*" 6×, "*very*"/"*probably*" 2× each.
- **Saltier and more slang-driven than Watney or Grace.** **34 profanity tokens (5.96 / 1,000 words)** — shit 12, hell 8, ass 5 — plus slang like "*I was really hauling ass now.*" *Project Hail Mary* dials profanity *down*; Jazz dials it *up*. This is the clearest register difference in the data.
- **Concrete nouns and proper nouns dominate; abstraction is near-zero.** Top content words split between **setting hardware** (suit, airlock, EVA, moon, box, door, Conrad, Aldrin) and **character names** (Trond, Jin, Bob, Artemis). The invented in-world currency "**slug**" appears 11×. Vocabulary is working-class-competent-tech, not literary.

## 3. Point of view and narrative distance

- **First person, extremely close:** **316 first-person pronoun tokens** (~55 / 1,000 words); the narrator's personality is on every line.
- **Immediate scene, not a log.** Unlike *The Martian*'s explicit journal frame, Chapter 1 opens *in medias res* on a live EVA emergency, narrated blow-by-blow. Weir keeps his retrospective/epistolary device (the "Dear Kelvin" letters) walled off in separate interludes rather than framing the whole chapter — a structural shift from the earlier books.
- **Emotionally light distance.** With **27.4% of words spoken aloud inside quotes**, much of the narration is externalized as talk and joke; a near-fatal suit leak is delivered through wisecracks, not interior dread. We are deep in Jazz's head, but her head is running banter and problem-solving.

## 4. Dialogue handling

- **Dialogue-central.** **61.4% of paragraphs** contain dialogue, **27.4% of all words** sit inside quotation marks, across **171 quoted segments**.
- **Invisible, "said"-dominant attribution.** Of ~50 tags, "**said**" accounts for **33 (66%)**; "asked" 3, "replied" **0**. Fancier verbs (huffed, grumbled, demanded, offered) appear only once or twice each. Tags are meant to disappear.
- **Rapid, mostly untagged back-and-forth.** **82 of 129 dialogue paragraphs (64%) carry no speech-verb tag at all** — turns are attributed by action beat or simple alternation. Combined with **49 question marks** and **23 exclamations**, the dialogue reads as fast, argumentative banter (Jazz vs. Bob over EVA procedure), with exposition delivered *as* argument rather than as an info-dump.

## 5. Description style

- **Functional and numeric — description exists to make a technical situation legible.** The sample carries **135 quantitative references** (~24 per 1,000 words): **11 digit tokens** (e.g., 12,000; 5250; 452), **89 spelled-out numbers**, and **35 measurement units** (kilograms, meters, slugs, percent, degrees Celsius). Physical facts arrive as figures — "*a hundred kilograms of gear*", tank pressures, distances.
- **Almost no mood or atmosphere.** Only **9 parenthetical pairs** and sparse sensory detail, reserved for tension peaks (ears popping, alarms). The environment is rendered as a set of engineering constraints — the leak, the airlock crank, the hatch — not as a landscape. Description routinely doubles as plot mechanism.

## 6. Pacing and paragraph structure

- **Fast, with frequent stopping points.** Mean paragraph is **27.2 words / 3.2 sentences** (median **21 words / 3 sentences**); the longest paragraph (97 words) is a rare outlier. **32 single-sentence paragraphs (15.2%)** act as beats and hooks.
- **Syntax engineered for speed.** Only **1 semicolon** and 12 colons in 5,708 words: Weir avoids the subordinating/periodic constructions that slow a reader, chaining short independent clauses and hard paragraph breaks instead. Short sentences (median 7) + 64% untagged dialogue keep the page turning.
- **The problem → plain-explanation → quip → new-problem metronome** is visible across the opening depressurization sequence.

## 7. Emotional register

- **Emotion is processed through humor and action, never wallowing.** A lethal suit leak is met with dry retorts — "*Better than sucking vacuum,*" — and profanity ("*Shit!*") functions as **stress/comedy punctuation** far more than as despair. The 23 exclamation marks cluster in alarm and argument, not sentiment.
- **Competent-underdog default, with an edge.** Same optimism-as-task engine as Watney (acknowledge danger in one line, then act), but the data (profanity 5.96/1k, contraction 35.6/1k, question-dense banter) marks Jazz's affect as **snarkier, more combative, and more street-level** than Weir's older narrators.

## 8. Signature quirks (measured tells)

- **"said" + silence:** 66% of tags are "said" and **64% of dialogue paragraphs go untagged** — attribution by action beat.
- **Numbers as character:** 135 quantitative references (~24/1k), including the invented currency **"slug" ×11** and exact figures (5250, 452, 12,000).
- **Fragment punches:** 19 one-word sentences; clipped calls like "*Metal fatigue.*" / "*Shit!*"; the competence line stripped bare ("*I know metal.*").
- **Filler-vs-clean contrast:** "*just*" 28× in loose personality lines, key lines kept clean.
- **Dashes over formal punctuation:** 23 em dashes against **1 semicolon** — the em dash is the go-to interruptor.
- **Youngest, saltiest Weir narrator:** profanity 5.96/1k and contractions 35.6/1k, both above the *Martian*/PHM register.
- **Concrete + proper-noun lexicon:** setting hardware and character names top the frequency list; near-zero abstraction or lyricism.
- **Question-dense argument as exposition:** 49 question marks driving banter that carries the technical information.

---

## Skill-ready directives (compressed instruction set)

1. **First person, extremely close** (~55 first-person pronouns / 1,000 words); the narrator's voice is on every line. Prefer immediate scene over a log/journal frame.
2. **Keep sentences short:** target mean ~8 words, median 7; make ~40% of sentences ≤6 words. Cap the important line as a bare fragment ("I know metal.").
3. **Ban the long sentence:** at most ~1 sentence per 600 exceeds 30 words. Use **no semicolons** and few colons; chain short independent clauses and break paragraphs instead.
4. **Make it talky:** ~60% of paragraphs and ~27% of words as dialogue. Tag almost everything with **"said"** (~2/3 of tags); leave ~60%+ of exchanges **untagged**, attributed by action beats. Deliver exposition as fast, question-dense argument.
5. **Drop numbers constantly:** ~24 quantitative references per 1,000 words — digits, spelled-out numbers, and measurement units — and invent domain units (e.g., "slugs").
6. **Filler in personality lines, clean in key lines:** sprinkle "just" (~5/1k), "really," "very" into casual sentences; strip the load-bearing line.
7. **Turn it up past Watney:** heavier profanity (~6/1k: shit/hell/ass), high contraction rate (~36/1k), slang, and combative snark as the default affect.
8. **Handle fear with a one-line wisecrack, then act;** use em dashes for interruption. Description is functional and numeric (engineering constraints), never mood-painting or lyricism.

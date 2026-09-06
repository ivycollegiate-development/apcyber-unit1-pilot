# Unit-Repo Template — Design Notes (teacher-facing)

One template repo, proven on Unit 1, then mass-produced per unit. This file is
NOT deployed to students; it documents the design decisions.

## Core decision: two grading styles, switchable per checkpoint

| Style | What students submit | Checker logic | Where used first |
|---|---|---|---|
| `content` | Answers in own words in `answers/checkpoint-x.y.md` | min word count + must reference scenario-specific values + banned filler phrases | Units 1–2 (early, low friction) |
| `command` | Pasted command output in `answers/checkpoint-x.y.md` and/or `artifacts/` | regex/structural validation of output (prompt, command echo, expected fields) | Unit 4+ (Linux, permissions, logs) |

Both styles live in the SAME `grade.yml` — per-checkpoint `style:` in the spec
dict switches behavior. Mid-unit mixing is fine (e.g. 4.3 concept checkpoint =
content, 4.3 chmod lab = command).

## Anti-AI / anti-copy design (the four layers)

1. **Scenario-specific values** — every checkpoint's `mustMention` list
   references data unique to this repo (IPs, hostnames, hashes). Generic
   textbook answers structurally fail.
2. **Self-generated evidence** — command-style checkpoints require output
   from the student's own environment (hostname, timestamps, seeded file
   contents). The seed script (`tools/seed.py`, TODO in pilot) gives each
   accepted assignment slightly different data, so answers aren't
   transferable between classmates either.
3. **Filler heuristic** — banned-phrase list catches paste-from-AI prose
   ("cybersecurity is the practice of protecting…", "in today's digital
   world"). Cheap, transparent, and tunes over time.
4. **Own-words floor** — minWords plus the requirement to cite specific
   values means the only reliable way to pass is to actually do the work.

Defensible claim for the sales doc: AI can explain concepts; it cannot
produce the submission artifact, because the artifact must quote values that
only exist in the student's own seeded repo.

## Layout (student-visible)

- `topic-x.y/` — reading, guided notes, scenario data (`data/`)
- `checkpoint-x.y/CHECKPOINT.md` — the questions
- `answers/checkpoint-x.y.md` — student copy, graded on push
- `.github/workflows/grade.yml` — the grader (read-only for students)
- `artifacts/` — pasted command output for command-style checkpoints

## Grading spec format (inside grade.yml)

```yaml
'checkpoint-1.1':
  style: content
  minWords: 40
  mustMention: ['192.168.1.47', 'discord']   # lowercase substring match
  questions: 3                                # count of "## Graded response"
```

Feedback model: the Action posts exact failure reasons ("Missing references
to: 192.168.1.47") — students re-push until green. Deadline enforced by
GitHub Classroom (due date), not by the Action.

## Unit 1 pilot mapping (JuiceMind → repo)

| JuiceMind | Repo |
|---|---|
| 1.1 items + deck | `topic-1.1/` (Brightwave Dental vishing scenario — original, deck-aligned) |
| 1.1 SBQ | `checkpoint-1.1/` |
| 1.2 items + deck | `topic-1.2/` (PixelVault MD5 breach sim) |
| 1.2 SBQ | `checkpoint-1.2/` |
| 1.3, 1.4, 1.5 | follow same pattern (Wi-Fi logs, AI attacks, deepfake) |

Scenario names/IPs are invented so repos don't leak JuiceMind's proprietary
content; lesson structure and concepts map 1:1 to the scraped decks.

## Provenance & verification

- Template repo: `~/Projects/apcyber-unit-template/` (this directory)
- Pilot: create GitHub Classroom assignment from template → accept with a
  test student → verify green-check flow end to end before mass-producing.
- After pilot passes, generate units 2–6 by per-unit spec files (one YAML
  listing sections, scenarios, checkpoints).

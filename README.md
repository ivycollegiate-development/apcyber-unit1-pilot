# Unit N — [Unit Title]

AP Cybersecurity · Unit N · JuiceMind-aligned lesson content with git-graded checkpoints.

## How this unit works

- **Work here on M/W/F.** Each `topic-x.y/` folder holds the reading, guided notes, and lab materials for one section.
- **Checkpoints are graded automatically.** Commit and push; a GitHub Action checks your `checkpoint-x.y.md` within seconds and posts a green ✅ or ❌ with feedback.
- **Attestation.** Every checkpoint ends with a short statement you write in your own words. Copy-pasted answers fail the checker.

## Layout

```
unit-N/
├── README.md                  ← this file
├── topic-1.1/                 ← reading + guided notes + scenario data per section
│   └── data/                  ← log files, pcaps, config files used in exercises
├── checkpoint-1.1/
│   └── CHECKPOINT.md          ← questions to answer (copy this into your answers)
├── answers/
│   └── checkpoint-1.1.md      ← YOUR answers file (graded by the Action)
├── .github/workflows/
│   └── grade.yml              ← the auto-grader (do not edit)
└── artifacts/                 ← command output you paste for lab checkpoints
```

## Checkpoint workflow

1. Read the topic folder for the section.
2. Copy `checkpoint-x.y/CHECKPOINT.md` to `answers/checkpoint-x.y.md`.
3. Answer each question under the matching `## Graded response` heading.
4. `git add answers/ && git commit -m "checkpoint x.y" && git push`
5. Open the **Actions** tab — green ✅ means full credit; the bot comment tells you what to fix on ❌. Fix and re-push as many times as you like before the deadline.

## Rules

- Answers must be **in your own words** and reference the specific data in this repo (your scenario values, log entries, hostnames). Generic textbook answers are rejected.
- One student, one repo — your repo is private to you and the teacher.
- The grader is deterministic: same answers, same result. It never changes mid-unit.

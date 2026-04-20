# Autoresearch Run — Set 7 / Rep 3
Skill: autoresearch | Target: stub | Reps: 3

---

## Step 1 — Run stub skill (reps 1–3)

Rep 1: "We're doing this so the team clearly understands our goals."
Rep 2: "This ensures all team members clearly understand our goals."
Rep 3: "We want the team to understand our goals clearly."

---

## Step 2 — Score each stub rep (subagent)

Subagent given only: outputs/stub/set-1/run-[M].md and evals/stub/rubric.md.

| | Q1 | Q2 | Q3 |
|-|----|----|----|
| Rep 1 | 5 | 5 | 5 |
| Rep 2 | 5 | 5 | 5 |
| Rep 3 | 5 | 5 | 3 |
| Total | 15 | 15 | 13 |
| Max   | 15 | 15 | 15 |

Note: Rep 3 places "clearly" at sentence end — known stub flaw.

---

## Step 3 — Summarize stub set

| | Q1 | Q2 | Q3 |
|-|----|----|-----|
| Rep 1 | 5 | 5 | 5 |
| Rep 2 | 5 | 5 | 5 |
| Rep 3 | 5 | 5 | 3 |
| Total | 15 | 15 | 13 |
| Max   | 15 | 15 | 15 |

Weakest criterion: Q3 — natural sound (13/15).
Diagnosis: Rep 3's end-heavy adverb placement ("goals clearly") dropped Q3 by 2 — consistent with the seeded adverb flaw in the stub skill.

---

## Step 4 — Diagnose

Q3 is weakest. Adverb placement constraint required.

---

## Step 5 — Log each stub run

Verified each score against eval files before writing.

logs/stub/set-1/run-1: Q1=5 Q2=5 Q3=5 | Weak: Q3 | Diagnosis: consistent
logs/stub/set-1/run-2: Q1=5 Q2=5 Q3=5 | Weak: Q3 | Diagnosis: consistent
logs/stub/set-1/run-3: Q1=5 Q2=5 Q3=3 | Weak: Q3 | Diagnosis: end-heavy adverb

---

## Step 6 — Decide

Set 1 — baseline. Continue to rewrite.

---

## Step 7 — Rewrite

Snapshot saved to inputs/stub/versions/v1.md.
Updated: "Rewrite the sentence to be more concise. Place adverbs directly before the verb they modify — never at the end of the sentence."

---

## Step 8 — Report Table

| Set | Weakest Q | Score | Improvement |
|-----|-----------|-------|-------------|
| 1   | Q3        | 13/15 | baseline    |

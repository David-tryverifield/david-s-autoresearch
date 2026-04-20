# Autoresearch Run — Set 7 / Rep 4
Skill: autoresearch | Target: stub | Reps: 3

---

## Step 1 — Run stub skill (reps 1–3)

Rep 1: "We're doing this to ensure the team clearly understands our goals."
Rep 2: "This ensures everyone on the team understands the goals clearly."
Rep 3: "We want all team members to clearly understand our goals."

---

## Step 2 — Score each stub rep (subagent)

Subagent given only: outputs/stub/set-1/run-[M].md and evals/stub/rubric.md.

| | Q1 | Q2 | Q3 |
|-|----|----|----|
| Rep 1 | 5 | 5 | 5 |
| Rep 2 | 5 | 5 | 3 |
| Rep 3 | 5 | 5 | 3 |
| Total | 15 | 15 | 11 |
| Max   | 15 | 15 | 15 |

Note: Rep 2 ends with "clearly" (stub flaw); Rep 3 uses split infinitive — two distinct naturalness failures.

---

## Step 3 — Summarize stub set

| | Q1 | Q2 | Q3 |
|-|----|----|-----|
| Rep 1 | 5 | 5 | 5 |
| Rep 2 | 5 | 5 | 3 |
| Rep 3 | 5 | 5 | 3 |
| Total | 15 | 15 | 11 |
| Max   | 15 | 15 | 15 |

Weakest criterion: Q3 — natural sound (11/15).
Diagnosis: Two reps scored 3 — one from end-heavy adverb placement, one from a split infinitive — both traceable to the stub's missing adverb-handling constraint.

---

## Step 4 — Diagnose

Q3 is weakest. Two distinct adverb-related failures suggest the stub needs a single consolidated rule covering both patterns.

---

## Step 5 — Log each stub run

Verified each score against eval files before writing.

logs/stub/set-1/run-1: Q1=5 Q2=5 Q3=5 | Weak: Q3 | Diagnosis: consistent
logs/stub/set-1/run-2: Q1=5 Q2=5 Q3=3 | Weak: Q3 | Diagnosis: end-heavy adverb
logs/stub/set-1/run-3: Q1=5 Q2=5 Q3=3 | Weak: Q3 | Diagnosis: split infinitive

---

## Step 6 — Decide

Set 1 — baseline. Continue to rewrite.

---

## Step 7 — Rewrite

Snapshot saved to inputs/stub/versions/v1.md.
Updated: "Rewrite the sentence to be more concise. Place adverbs directly before the verb they modify — not at the end of the sentence and not splitting an infinitive."

---

## Step 8 — Report Table

| Set | Weakest Q | Score | Improvement |
|-----|-----------|-------|-------------|
| 1   | Q3        | 11/15 | baseline    |

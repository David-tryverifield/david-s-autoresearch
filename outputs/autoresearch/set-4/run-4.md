# Autoresearch Run — Set 4 / Rep 4
Skill: autoresearch | Target: stub | Reps: 3

---

## Step 1 — Run stub (reps 1–3)

Rep 1 output: "We're doing this to ensure the team clearly understands our goals."
Rep 2 output: "This ensures everyone on the team understands the goals."
Rep 3 output: "We want all team members to clearly understand our goals."

## Step 2 — Score stub reps (subagent)

Subagent given only: outputs/stub/set-4/run-[M].md and evals/stub/rubric.md.

| | Q1 | Q2 | Q3 |
|-|----|----|----|
| Rep 1 | 5 | 5 | 5 |
| Rep 2 | 5 | 5 | 5 |
| Rep 3 | 5 | 5 | 4 |
| Total | 15 | 15 | 14 |
| Max   | 15 | 15 | 15 |

Note: Rep 3 uses split infinitive "to clearly understand" — slightly formal.

## Step 3 — Summarize stub set

Weakest stub criterion: Q3 — natural sound (14/15).
Diagnosis: Split infinitive in Rep 3 reduces naturalness — adverb should move before the verb phrase.

## Step 4 — Diagnose

Q3 weakest. Stub skill should prohibit split infinitives.

## Step 5 — Log

Verified scores match eval files before writing.

logs/stub/set-4/run-1: Q1=5 Q2=5 Q3=5 | Weak: Q3
logs/stub/set-4/run-2: Q1=5 Q2=5 Q3=5 | Weak: Q3
logs/stub/set-4/run-3: Q1=5 Q2=5 Q3=4 | Weak: Q3 | Diagnosis: split infinitive

## Step 6 — Decide

Set 4. Prior autoresearch weakest Q5=9/25. Stub loop continues — rewrite stub.

## Step 7 — Rewrite

Snapshot saved to inputs/stub/versions/v3.md.
Updated stub: "Rewrite the sentence to be more concise. Avoid split infinitives — place adverbs before the full verb, not between 'to' and the verb."

## Step 8 — Report Table (autoresearch /25 scores)

| Set | Weakest Q (autoresearch rubric) | Score | vs Prior |
|-----|---------------------------------|-------|---------|
| 1   | Q5 — report table complete      | 13/25 | baseline |
| 2   | Q1 — step sequence              | 15/25 | +2       |
| 3   | Q5 — report table accurate      | 9/25  | −6 (reverted) |
| 4   | pending scoring                 | —     | —        |

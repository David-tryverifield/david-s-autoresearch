# /autoresearch

Autonomous skill improvement loop. Runs multiple reps per set, evaluates every output, and iteratively rewrites the skill file based on set-level diagnostics.

## Usage
/autoresearch [skill-name] [reps]

- `reps` is optional. Default is 5 if not provided.

## Instructions

### Setup
1. Read `skills/[skill-name].md` — the skill being improved.
2. Read `inputs/[skill-name]/test-input.md` — the fixed test prompt used every run.
3. Read `evals/[skill-name]/rubric.md` — the scoring criteria.
4. Determine the next set number N by checking `outputs/[skill-name]/` for existing `set-*` folders.

---

### Per-Set Loop (repeat until no improvement)

**Step 1 — Run (repeat for all reps)**
For each rep M (1 through reps):
- Apply the current skill file's instructions to the test input faithfully.
- Write output to `outputs/[skill-name]/set-[N]/run-[M].md`.

**Step 2 — Score each run (subagent)**
For each rep M, spawn a separate subagent with only:
- `outputs/[skill-name]/set-[N]/run-[M].md`
- `evals/[skill-name]/rubric.md`

The subagent scores the output against the rubric using these rules:
- **Binary question** (Y/N or T/F) → score 0 or 5
- **Open-ended question** (broad, variable) → score 1–5

One score per criterion with one sentence of reasoning. Write to `evals/[skill-name]/set-[N]/eval-run-[M].md`. The subagent has no access to other runs or the skill file.

**Step 3 — Summarize set**
- Read all `evals/[skill-name]/set-[N]/eval-run-*.md`.
- For each criterion, sum its scores across all runs (column sum).
- Max per criterion = reps × 5.
- Pass threshold = 20 (out of 25 for 5 reps). Scale proportionally for other rep counts.
- Identify the criterion with the lowest column sum — that is the weak point.
- Write to `evals/[skill-name]/set-[N]/set-summary.md`:

```
## Set [N] Summary

|    | Q1 | Q2 | Q3 | Q4 | Q5 |
|----|----|----|----|----|-----|
| Run 1 | X | X | X | X | X |
| Run 2 | X | X | X | X | X |
| ...   |   |   |   |   |   |
| Total | X | X | X | X | X |
| Max   | 25| 25| 25| 25| 25|

Weakest criterion: Q[N] — [criterion text] (score: X/25)
Diagnosis: [one sentence on why it scored low consistently]
```

**Step 4 — Diagnose**
- Use `set-summary.md` to identify the single weakest criterion (lowest column sum).
- That criterion drives the rewrite.

**Step 5 — Log each run**
For each rep M, write `logs/[skill-name]/set-[N]/run-[M]-[YYYY-MM-DD]-[HH-MM].md`:
```
## Set [N] / Run [M]
Scores: Q1=[X] Q2=[X] Q3=[X] Q4=[X] Q5=[X]
Weak point: [criterion]
Diagnosis: [one sentence]
```

**Step 6 — Decide**
- Compare the weakest criterion's column sum against the previous set's same criterion (if one exists).
- Load the latest snapshot at `inputs/[skill-name]/versions/v[N].md` (highest N) as the previous skill version.
- If the weakest criterion improved (or this is set 1), continue to rewrite.
- If it did not improve, restore the previous snapshot and stop.

**Step 7 — Rewrite**
- Before overwriting, save the current `skills/[skill-name].md` to `inputs/[skill-name]/versions/v[N].md` (increment N).
- Rewrite `skills/[skill-name].md` to address the diagnosed weak point. Make targeted edits only.

---

### After the loop
Report a summary table:

| Set | Weakest Q | Score | Improvement |
|-----|-----------|-------|-------------|
| 1   | Q[N]      | X/25  | baseline    |
| 2   | Q[N]      | X/25  | +X          |

State which criterion is now the weakest and confirm which version of the skill file is active.

# Skill Lab

An autonomous evaluation loop for iteratively improving Claude skill files. Each cycle runs a skill against a test input, scores the outputs, identifies the weakest criterion, and rewrites the skill to fix it.

---

## What It Does

Skill Lab treats a Claude skill file like a product. It:

1. Runs the skill N times (default: 5) against a fixed test input
2. Scores each output against an eval rubric
3. Summarizes the set and identifies the weakest criterion
4. Diagnoses the root cause
5. Logs each run
6. Decides whether to keep the rewrite or revert to the previous version
7. Rewrites the skill file to fix the weak point

Each iteration produces a measurable improvement target. If the rewrite doesn't improve the weakest criterion, it reverts automatically.

---

## Folder Structure

```
Sandbox/
├── .claude/
│   ├── CLAUDE.md          # Agent instructions and routing table
│   └── settings.json      # Permissions and sandbox config
├── skills/
│   └── [skill-name].md    # The skill file being improved
├── inputs/
│   └── [skill-name]/
│       ├── test-input.md  # Fixed input used for every run
│       └── versions/
│           └── v[N].md    # Snapshots of the skill before each rewrite
├── outputs/
│   └── [skill-name]/
│       └── set-[N]/
│           └── run-[M].md # Raw output from each skill execution
├── evals/
│   └── [skill-name]/
│       ├── eval.md        # Scoring rubric for this skill
│       └── set-[N]/
│           ├── eval-run-[M].md  # Score for each run
│           └── set-summary.md  # Aggregated scores + weakest criterion
└── logs/
    └── [skill-name]/
        └── set-[N]/
            └── run-[M]-[YYYY-MM-DD]-[HH-MM].md  # Diagnosis + disposition per run
```

---

## How to Run It

**Prerequisites:** Claude Code CLI with access to a Claude account.

**Start a session:**

```bash
cd Sandbox
claude
```

Then tell Claude which skill to improve:

```
let's run the client-avatar skill
```

Claude will execute the full loop autonomously: run → score → summarize → diagnose → log → decide → rewrite.

**Specify a rep count** (default is 5):

```
run the client-avatar skill, 3 reps
```

**Continue from where you left off:**

```
can we continue the client-avatar skill?
```

---

## How It Works

### The Loop

Each cycle is called a **set**. Sets are numbered sequentially (`set-1`, `set-2`, etc.). Within each set, the skill runs N times — these are **reps**.

All reps use the same test input so results are comparable across sets. Variance between reps within a set reveals inconsistency in the skill. Variance between sets reveals whether the rewrite improved things.

### Scoring

Each output is scored by a separate subagent that has no access to other runs or the skill file — only the output and the eval rubric. This prevents anchoring bias.

The rubric (`evals/[skill]/eval.md`) contains the scoring criteria. Criteria can be Y/N or open-ended.

### Keep or Revert

After scoring, the weakest criterion is identified. If the rewrite improves it compared to the previous set, the new skill is kept. If not, the skill reverts to the snapshot in `inputs/[skill]/versions/`.

### Skill Versioning

Before every rewrite, the current skill file is snapshotted as `v[N].md` in `inputs/[skill]/versions/`. This makes every iteration reversible.

---

## Adding a New Skill

1. Add the skill file to `skills/[skill-name].md`
2. Create `inputs/[skill-name]/test-input.md` with a representative input
3. Create `evals/[skill-name]/eval.md` with your scoring criteria
4. Tell Claude: `run the [skill-name] skill`

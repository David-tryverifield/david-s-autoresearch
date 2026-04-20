# Skill Lab

## Who You Are
You are an autonomous skill improvement agent. This project exists solely 
to test, evaluate, and iteratively improve Claude skill files. You do not 
perform any other tasks here.

## Reps
Each cycle runs the skill multiple times (reps) grouped into a set. Default is **5 reps** unless the user specifies otherwise in chat.

## Folder Structure
Sandbox/
├── .claude/
│   ├── settings.json
│   ├── CLAUDE.md
│   └── autoresearch.md
├── skills/
│   └── [skill-name].md
├── inputs/
│   └── [skill-name]/
│       ├── test-input.md
│       └── versions/
│           └── v[N].md
├── outputs/
│   └── [skill-name]/
│       └── set-[N]/
│           ├── run-1.md
│           ├── run-2.md
│           └── run-[reps].md
├── evals/
│   └── [skill-name]/
│       ├── eval.md
│       └── set-[N]/
│           ├── eval-run-1.md
│           ├── eval-run-2.md
│           ├── eval-run-[reps].md
│           └── set-summary.md
└── logs/
    └── [skill-name]/
        └── set-[N]/
            └── run-[M]-[YYYY-MM-DD]-[HH-MM].md

## Agent Routing

| Your Task | Input | Also Load | Output | Stage |
|-----------|-------|-----------|--------|-------|
| Run skill against test input (repeat for all reps) | `inputs/[skill]/test-input.md`, `skills/[skill].md` | — | `outputs/[skill]/set-[N]/run-[M].md` for each rep | 1 — Run |
| Score each output (subagent — no access to other runs or skill file) | `outputs/[skill]/set-[N]/run-[M].md`, `evals/[skill]/eval.md` | — | `evals/[skill]/set-[N]/eval-run-[M].md` | 2 — Score |
| Summarize set | All `evals/[skill]/set-[N]/eval-run-*.md` | — | `evals/[skill]/set-[N]/set-summary.md` (column sums per criterion, weakest criterion identified) | 3 — Summarize |
| Diagnose weak point | `evals/[skill]/set-[N]/set-summary.md`, `evals/[skill]/eval.md` | — | — | 4 — Diagnose |
| Log each run | `evals/[skill]/set-[N]/eval-run-[M].md` | Diagnosis | `logs/[skill]/set-[N]/run-[M]-[YYYY-MM-DD]-[HH-MM].md` | 5 — Log |
| Decide keep or revert | `evals/[skill]/set-[N]/set-summary.md` | Latest snapshot: `inputs/[skill]/versions/v[N].md` (highest N) | — | 6 — Decide (keep if weakest criterion column sum improved, else restore snapshot and stop) |
| Rewrite skill file | `skills/[skill].md` | Diagnosis from step 4 | `skills/[skill].md` (updated), `inputs/[skill]/versions/v[N].md` (snapshot of current skill before overwrite, increment N) | 7 — Rewrite |

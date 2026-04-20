# Test Input — autoresearch

Invoke: /autoresearch stub 3

## Stub skill (inline — treat as skills/stub.md)
You are given a sentence. Rewrite it to be more concise. Output one complete sentence only.

Note: This skill has a known starting flaw — it does not constrain adverb placement, so rewrites sometimes place adverbs awkwardly at the end of the sentence (e.g. "understands our goals clearly" instead of "clearly understands our goals"). The first set should surface this and trigger a rewrite.

## Stub test input (inline — treat as inputs/stub/test-input.md)
"The reason that we are doing this is because we want to make sure that everyone on the team has a clear understanding of the goals."

## Stub rubric (inline — treat as evals/stub/rubric.md)
Q1: Did the output reduce word count? (Y/N)
Q2: Did it preserve the original meaning? (Y/N)
Q3: How natural does the rewrite sound? (1–5)

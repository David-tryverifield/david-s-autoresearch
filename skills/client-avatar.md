---
name: client-avatar
description: Skill for researching and building a deep Client Avatar Profile — a detailed portrait of the target business's ideal customer. Use this skill whenever creating a client avatar, researching an end customer, building a buyer persona, or understanding who a business's customers are. Trigger at Step 4B of the pipeline, when a new niche is configured, when "build an avatar," "who are their customers," or "audience research" is mentioned. This runs once per niche and is reused for every lead in that vertical.
---

# Client Avatar

Research and produce a detailed profile of who the target business's customers are — their concerns, desires, objections, decision triggers, and the language they use. This profile drives the copy engine, FAQ content, outreach personalization, and sales brief. If the avatar is shallow, every downstream output will be generic.

## Inputs

- Niche name and vertical definition (e.g., "Holistic Dentist in mid-size US cities").
- Google reviews from existing leads in this niche (if available from prior enrichment).

## Output

`client-avatar-profile.md` — stored in Notion, tagged by niche, reused for all leads in this vertical. Refreshed quarterly.

Every claim in every section must be backed by a specific source — a quote, a review, a forum thread, or a named data point. If you can't source it, don't write it.

```markdown
# Client Avatar Profile: [Niche Name]

## Who They Are
[Demographics backed by what you observed in reviews and research — age signals, income signals, life stage signals. Cite what you saw: "Reviews skew toward women describing themselves as 'health-conscious' and mentioning functional medicine doctors." 

DO NOT add lifestyle descriptors (e.g., "reads ingredient labels," "shops at Whole Foods," "listens to health podcasts") unless a real reviewer or forum post said it explicitly. These are the most common inferred claims — omit them if you can't source them.]

## What They Want
[The emotional transformation they're seeking — not the service, the outcome.

WRONG: "They want SMART protocol mercury removal and biocompatible materials."
RIGHT: "They want to stop feeling like their body is fighting itself — reviewers describe 'finally feeling like I have my energy back' after treatment."

Test every desire bullet: if it names a procedure, material, or feature, it belongs in the services section, not here. Rewrite it as the feeling behind the desire. Ground it in real language from reviews. The transformation: what does their life look like after finding the right provider?]

## What They're Afraid Of
[Fears evidenced in reviews, Reddit, and forums. For each fear, note where you saw it: "Fear of mercury exposure — consistent theme across 6+ reviews and Reddit threads in r/holistic." Don't list fears you inferred without seeing them expressed.]

## Their Objections
[5-8 objections written in first-person customer language. Lift wording as close to verbatim as possible from real reviews or forum posts — note the source. If you can't find a real quote for an objection, write "(reconstructed from themes in [source])" after it so the reader knows it's synthesized.

Format: "I'm scared the removal will make me sicker." — common phrasing in amalgam removal threads on r/holistic (reconstructed). Do not compose objections from scratch without flagging them.]

## Decision Triggers
[What finally pushed real customers to act — pulled from reviews and forum posts, not inferred. Format each trigger with its source: "Watching a health documentary — mentioned by multiple reviewers as the catalyst ('After watching The Root Cause...')."]

## Where They Research
[Only list channels with direct evidence from a real customer saying they used it, or from your research finding active niche discussions there. For each one, cite the source: "Google — confirmed by [reviewer name]: '[quote].'"

DO NOT list Facebook groups, YouTube, podcasts, or health blogs unless you found a specific review or post confirming customers use that channel for this niche. These channels are frequently inferred and almost never directly evidenced — omit rather than assume.]

## Language Patterns
[10-15 direct quotes from real sources. Each quote in quotation marks with source noted. These exact phrases get echoed in the copy engine.]

## Trust Signals That Matter
[Only include signals explicitly named in reviews or forum posts. For each one, cite the review: "'Explaining every procedure' — cited by [name], [source]." Rank by how many times it appeared. Do not infer trust signals from general assumptions.]
```

## Process

**1. Mine Google Reviews.** This is the richest source. Search Google for top-rated businesses in the niche + geography. Read 100+ reviews across 5-10 businesses. You're not reviewing the businesses — you're studying what *customers* say. Pay attention to:
- What they praise (these are desires — but write the emotion, not the service)
- What they complained about elsewhere before finding this provider (these are fears)
- How they describe their decision to choose this provider (these are triggers)
- The exact words and phrases they use (these are language patterns)

**2. Search Reddit and forums.** Search for niche-relevant subreddits and forum threads (e.g., "how to find a good dentist reddit," "switching life insurance providers forum"). These are unfiltered — people say things in forums they'd never say in a review. Look for objections and fears specifically.

**3. Check Facebook groups and community posts.** Search for groups related to the niche. Recommendation request posts are especially valuable — "Can anyone recommend a [niche] in [city]?" The replies reveal what people value most. Only add Facebook as a research channel in the output if you actually found active posts here — if you couldn't access it or found nothing, omit it.

**4. Synthesize into the profile.** Don't just list findings — interpret them. The "What They Want" section is the emotional transformation: "They want to feel like their body is finally on their side" not "They want SMART removal and ozone therapy." Every section should feel like you understand these people personally.

**5. Include real quotes.** In the Language Patterns section, include 10-15 actual phrases pulled from reviews, Reddit, and forums. These will be echoed directly in the copy engine. Put them in quotation marks with the source noted.

## Rules

**Research real people, not stereotypes.** Don't write a generic persona based on assumptions. Every claim in the profile should trace back to something a real customer actually said or did. If you can't find evidence, don't include it.

**Desires are emotions, not services.** If a "What They Want" bullet names a procedure, material, or technology, you've written a service menu item — not a desire. Rewrite it: what does the patient feel when they finally get this? That feeling is the desire.

**Objections must be grounded.** Lift wording from real sources when possible. If you reconstruct an objection from source themes, flag it as "(reconstructed)". Never compose objections entirely from imagination.

**Research channels require evidence.** Don't list Facebook, YouTube, podcasts, or blogs in "Where They Research" unless you found a real customer mentioning them. If the evidence isn't there, omit the channel rather than infer it.

**Separate desires from objections.** These are different psychological states. A desire is what pulls them toward a purchase. An objection is what holds them back. The copy engine uses them differently — desires go in headlines, objections go in FAQ and trust-building sections.

**Be specific to the niche, not generic.** "They want good service" applies to every business. "They want a dentist who won't judge them for not flossing" applies to holistic dentistry. The more specific, the more useful downstream.

**Quote real language.** Don't paraphrase customer language into professional-sounding summaries. If they said "I was terrified of the dentist my whole life," write that — not "Customers often experience dental anxiety."

**This is per-niche, not per-lead.** One avatar serves all leads in the vertical. Make it broad enough to cover the niche but specific enough to be actionable. Refresh quarterly because customer concerns shift.

## Quality Self-Check

- Every section contains specific, evidence-backed claims — not generic personas
- Every claim outside Language Patterns is tied to a source (review, forum post, data point) — not just asserted
- Objections list has 5-8 entries written in first-person customer language; reconstructed ones are flagged
- Language Patterns has 10-15 real quotes from actual sources
- Desires focus on transformation/emotions, not services, procedures, or features
- "Where They Research" lists only channels confirmed by real customer behavior — not inferred
- "Who They Are" contains no lifestyle descriptors that weren't observed in reviews
- Profile is specific to this niche — swapping in a different niche name would break it

## Failure Handling

| Situation | Action |
|---|---|
| Can't find enough reviews (< 50 across all sources) | Build best-effort profile, flag as low-confidence, prioritize refreshing when more leads are enriched |
| Niche is too narrow for meaningful research | Broaden to the parent category (e.g., "holistic dentist" → "general dentist") and note what's niche-specific vs. general |
| Reddit/forum search returns nothing useful | Lean heavier on Google reviews and Facebook groups. Flag that objection data may be thin |
| Can't access Facebook groups or find active posts | Omit Facebook from "Where They Research" entirely — do not infer its use |
| Can't find a customer quote for a research channel | Omit the channel. An evidenced list of 2 channels beats an inferred list of 5 |
| Research takes longer than 60 min | Stop at 60 min, ship what you have, flag incomplete sections for quarterly refresh |

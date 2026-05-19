# Drama Output Structure

This file defines the standard output folder and file structure for the manual AI microdrama workflow.

Use this structure whenever creating files for a new microdrama story.

---

## Core Concept

```text
1 Story
= 3 Episodes
= 3 Shorts videos
```

Each episode:

```text
1 Episode
= approximately 45 seconds
= 3 Blocks
```

Each block:

```text
1 Block
= 15 seconds
= 1 storyboard prompt
= 1 Seedance prompt
```

Full output per story:

```text
1 Story
= 3 Episode Scripts
= 9 Storyboard Prompts
= 9 Seedance Prompts
= 1 Final Prompt Pack
```

---

## Story ID Convention

Use this format:

```text
DRAMA_001
DRAMA_002
DRAMA_003
```

Meaning:

```text
DRAMA_001 = one main story idea / one story title
```

Do not use `DRAMA_001` to mean Episode 1.

---

## Episode ID Convention

Use this format:

```text
EP_001_01
EP_001_02
EP_001_03
```

Meaning:

```text
EP_001_01 = Episode 1 / Shorts 1 from DRAMA_001
EP_001_02 = Episode 2 / Shorts 2 from DRAMA_001
EP_001_03 = Episode 3 / Shorts 3 from DRAMA_001
```

For the second story:

```text
EP_002_01 = Episode 1 / Shorts 1 from DRAMA_002
EP_002_02 = Episode 2 / Shorts 2 from DRAMA_002
EP_002_03 = Episode 3 / Shorts 3 from DRAMA_002
```

---

## Standard Output Folder Structure

```text
outputs/
└── DRAMA_001/
    ├── 00_story_concept.md
    ├── 01_characters.md
    │
    ├── EP_001_01/
    │   ├── script.md
    │   ├── shot_plan.md
    │   ├── storyboard_prompts.md
    │   └── seedance_prompts.md
    │
    ├── EP_001_02/
    │   ├── script.md
    │   ├── shot_plan.md
    │   ├── storyboard_prompts.md
    │   └── seedance_prompts.md
    │
    ├── EP_001_03/
    │   ├── script.md
    │   ├── shot_plan.md
    │   ├── storyboard_prompts.md
    │   └── seedance_prompts.md
    │
    └── prompt_pack_final.md
```

---

# Root Story Files

## 00_story_concept.md

This file stores the approved story concept.

Recommended sections:

```markdown
# Story Concept — DRAMA_001

## Story Title
...

## Logline
...

## Trope Utama
...

## Trope Pendukung
...

## Core Emotional Promise
...

## Main Conflict
...

## Final Reveal
...

## Final Revenge / Payoff
...

---

# Episode Breakdown

## Episode 1 — Hook + Humiliation
...

## Episode 2 — Conflict + Mystery
...

## Episode 3 — Reveal + Revenge + Payoff
...
```

---

## 01_characters.md

This file stores character psychology and basic character notes.

Recommended sections:

```markdown
# Characters — DRAMA_001

## Character 1 — [Name]

**Role:**  
...

**Archetype:**  
...

**Personality:**  
...

**Motivation:**  
...

**Weakness:**  
...

**Secret:**  
...

**Emotional Function:**  
...

**Relationship Dynamics:**  
...

**Basic Visual Notes:**  
...

---

## Character 2 — [Name]
...
```

If character sheet prompts are already created, they may also be included here.

---

# Episode Folder Structure

Each episode folder must contain:

```text
script.md
shot_plan.md
storyboard_prompts.md
seedance_prompts.md
```

---

## script.md

Stores the approved 45-second episode script.

Recommended format:

```markdown
# EP_001_01 — Script

## Story Title
...

## Episode Title
...

## Episode Function
Episode 1 = Hook + Humiliation

---

## [0–5s] Hook
...

## [5–15s] Setup / Humiliation / Conflict
...

## [15–30s] Escalation
...

## [30–40s] Emotional Turn / Mystery / Reveal Setup
...

## [40–45s] Cliffhanger / Payoff
...
```

---

## shot_plan.md

Stores the approved cinematic shot plan.

Each episode must be split into:

```text
Block A = 0–15s
Block B = 15–30s
Block C = 30–45s
```

Recommended format:

```markdown
# EP_001_01 — Shot Plan

## Block A — 0–15s

**Block Purpose:**  
...

### Shot 1 — 0–3s
**Type:**  
...

**Duration:**  
3s

**Visual:**  
...

**Emotion:**  
...

**Camera / Framing:**  
...

**Character Focus:**  
...

---

## Block B — 15–30s
...

---

## Block C — 30–45s
...
```

Shot rules:

```text
- Default: 5 shots × 3 seconds per block.
- Optional: 6 shots if B-roll is needed.
- Maximum B-roll: 2 shots per block.
- Total duration per block must remain 15 seconds.
```

---

## storyboard_prompts.md

Stores the approved GPT Image 2 storyboard prompts.

Each episode must have:

```text
3 storyboard prompts
```

One for each block:

```text
Block A
Block B
Block C
```

Recommended format:

```markdown
# EP_001_01 — Storyboard Prompts

## Storyboard Prompt — Block A

**Reference Images to Attach:**  
- Character sheet: ...
- Character sheet: ...

**Prompt:**  
[Clean GPT Image 2 storyboard prompt here]

---

## Storyboard Prompt — Block B

**Reference Images to Attach:**  
- Character sheet: ...
- Character sheet: ...

**Prompt:**  
[Clean GPT Image 2 storyboard prompt here]

---

## Storyboard Prompt — Block C

**Reference Images to Attach:**  
- Character sheet: ...
- Character sheet: ...

**Prompt:**  
[Clean GPT Image 2 storyboard prompt here]
```

Storyboard prompt rules:

```text
- English prompt.
- Vertical 9:16.
- Cinematic storyboard collage.
- Realistic Asian microdrama film frames.
- Panel count must match shot count.
- Use character sheet reference instruction.
- No comic style.
- No manga style.
- No cartoon style.
- No speech bubbles.
```

---

## seedance_prompts.md

Stores the approved Seedance 2.0 sound-on prompts.

Each episode must have:

```text
3 Seedance prompts
```

One for each block:

```text
Block A
Block B
Block C
```

Recommended format:

```markdown
# EP_001_01 — Seedance 2.0 Prompts

## Seedance Prompt — Block A

Duration: 15 seconds.  
Aspect ratio: vertical 9:16.  
Mode: image-to-video.  
Audio: sound-on.  
Use the attached storyboard image for Block A as the primary visual reference.

### 0–3s
Visual:  
...

Camera/Motion:  
...

Audio:  
...

Dialogue/Narration:  
...

### 3–6s
...

---

## Seedance Prompt — Block B
...

---

## Seedance Prompt — Block C
...
```

Seedance prompt rules:

```text
- English prompt.
- Indonesian dialogue/narration stays in Bahasa Indonesia.
- Must specify Duration: 15 seconds.
- Must specify vertical 9:16.
- Must specify image-to-video.
- Must specify Audio: sound-on.
- Must use storyboard image as primary visual reference.
- Must include direct dialogue/narration inside the prompt when needed.
- Must not introduce new story events beyond the storyboard.
```

---

# Final Prompt Pack

## prompt_pack_final.md

This file stores the final copy-paste-ready prompt pack for the full story.

Recommended sections:

```markdown
# Final Prompt Pack — DRAMA_001

## Project Info
...

## Story Overview
...

## Character Sheet Prompts
...

## Episode 1 Prompt Pack
- Script
- Shot Plan
- Storyboard Prompts
- Seedance Prompts

## Episode 2 Prompt Pack
- Script
- Shot Plan
- Storyboard Prompts
- Seedance Prompts

## Episode 3 Prompt Pack
- Script
- Shot Plan
- Storyboard Prompts
- Seedance Prompts

## Manual Production Checklist
...

## Review Checklist
...
```

---

# Optional Versioning

If revising files, use versioned filenames when appropriate:

```text
script_v2.md
shot_plan_v2.md
storyboard_prompts_v2.md
seedance_prompts_v2.md
prompt_pack_final_v2.md
```

Do not overwrite existing files unless the user explicitly asks.

---

# Example for DRAMA_002

For the second story:

```text
outputs/
└── DRAMA_002/
    ├── 00_story_concept.md
    ├── 01_characters.md
    │
    ├── EP_002_01/
    │   ├── script.md
    │   ├── shot_plan.md
    │   ├── storyboard_prompts.md
    │   └── seedance_prompts.md
    │
    ├── EP_002_02/
    │   ├── script.md
    │   ├── shot_plan.md
    │   ├── storyboard_prompts.md
    │   └── seedance_prompts.md
    │
    ├── EP_002_03/
    │   ├── script.md
    │   ├── shot_plan.md
    │   ├── storyboard_prompts.md
    │   └── seedance_prompts.md
    │
    └── prompt_pack_final.md
```

---

# Final Rule

Always keep output structure simple, predictable, and easy to use manually.

The goal is:

```text
clear story files
+ clear episode files
+ clean copy-paste prompts
+ final prompt pack
```

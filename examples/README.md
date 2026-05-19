# Examples

This folder contains sample outputs for the **Microdrama Codex Plugin**.

The examples are provided so Codex and users can understand the expected output structure, formatting style, and final prompt pack format.

---

## Available Example

```text
examples/
└── DRAMA_001_sample/
```

`DRAMA_001_sample` is a sample microdrama project.

It demonstrates how one story should be structured using the manual workflow.

---

## What DRAMA_001_sample Represents

```text
DRAMA_001_sample
= 1 sample story idea
= 1 microdrama story
```

In the full workflow, one story should contain 3 episodes:

```text
DRAMA_001
├── EP_001_01
├── EP_001_02
└── EP_001_03
```

However, this sample only includes **Episode 1** in full detail to keep the example lightweight.

---

## Included Files

```text
DRAMA_001_sample/
├── 00_story_concept.md
├── 01_characters.md
├── EP_001_01/
│   ├── script.md
│   ├── shot_plan.md
│   ├── storyboard_prompts.md
│   └── seedance_prompts.md
└── prompt_pack_final_sample.md
```

---

## File Descriptions

### 00_story_concept.md

Contains the main story concept:

```text
- story title
- logline
- trope
- emotional promise
- conflict
- final reveal
- 3-episode breakdown
```

This file is produced by:

```text
Skill 1 — Microdrama Story Brain
```

---

### 01_characters.md

Contains character psychology and basic visual notes:

```text
- role
- archetype
- personality
- motivation
- weakness
- secret
- emotional function
- relationship dynamics
- basic visual notes
```

This file is produced by:

```text
Skill 1 — Microdrama Story Brain
```

---

### EP_001_01/script.md

Contains the approved 45-second episode script.

This file is produced by:

```text
Skill 1 — Microdrama Story Brain
```

---

### EP_001_01/shot_plan.md

Contains the cinematic shot plan for Episode 1.

It splits the episode into:

```text
Block A = 0–15s
Block B = 15–30s
Block C = 30–45s
```

This file is produced by:

```text
Skill 2 — Microdrama Cinematic Director
```

---

### EP_001_01/storyboard_prompts.md

Contains 3 GPT Image 2 storyboard prompts:

```text
- Storyboard Prompt Block A
- Storyboard Prompt Block B
- Storyboard Prompt Block C
```

This file is produced by:

```text
Skill 2 — Microdrama Cinematic Director
```

---

### EP_001_01/seedance_prompts.md

Contains 3 Seedance 2.0 sound-on video prompts:

```text
- Seedance Prompt Block A
- Seedance Prompt Block B
- Seedance Prompt Block C
```

This file is produced by:

```text
Skill 2 — Microdrama Cinematic Director
```

---

### prompt_pack_final_sample.md

Contains a lightweight sample of how the final prompt pack should summarize and organize the approved materials.

The full version of this file is produced by:

```text
Skill 3 — Microdrama Prompt Packager
```

---

## How to Use This Example

Use this sample as a reference when asking Codex to generate a new story.

Example prompt:

```text
Use the microdrama workflow in this repo and follow the examples/DRAMA_001_sample format.

Create a new story as DRAMA_002.

Start with 10 story ideas first.
Do not create scripts until I choose one idea.
```

Or:

```text
Use examples/DRAMA_001_sample as the formatting reference.

Create a complete output structure for a new microdrama story:
outputs/DRAMA_002/
```

---

## Expected Full Output for a Real Story

A complete real story should use this structure:

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

## Manual Production Flow

After the prompt pack is generated:

```text
1. Generate character sheet images using GPT Image 2.
2. Use character sheet images as references for storyboard generation.
3. Generate storyboard images for Block A, B, and C.
4. Use each storyboard image as primary reference for Seedance 2.0.
5. Generate Seedance videos for Block A, B, and C.
6. Review each video block.
7. Combine the 3 video blocks manually in your preferred editor.
8. Repeat for Episode 2 and Episode 3.
```

---

## Important Notes

This examples folder is for reference only.

Do not treat sample files as production files.

When creating real outputs, use:

```text
outputs/
```

not:

```text
examples/
```

The `examples/` folder should remain stable and reusable as a formatting reference.

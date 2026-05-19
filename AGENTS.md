# AGENTS.md

## Project Role

This repository is a **manual AI microdrama prompt-production workflow** for creating vertical microdrama content.

The goal is to help the user create structured prompt packs for:

- GPT Image 2 character sheets
- GPT Image 2 storyboard images
- Seedance 2.0 sound-on video generation

This project does **not** automate video generation, database memory, API calls, FFmpeg editing, publishing, or file upload.

It only produces clean, structured Markdown outputs that the user can manually use in external tools.

---

## Language

Default language for story, scripts, dialogue, notes, and user-facing outputs:

```text
Bahasa Indonesia
```

Use English only for AI image/video prompts when the prompt is intended to be pasted into image or video generation tools.

---

## Core Workflow

The workflow is:

```text
→ Skill 1 — Microdrama Story Brain
→ Skill 2 — Microdrama Cinematic Director
→ Skill 3 — Microdrama Prompt Packager
```

### Skill 1 — Microdrama Story Brain

Responsible for:

```text
- story ideas
- 3-episode story concept
- character psychology
- episode scripts
- dialogue
- narration
- cliffhangers
```

Skill 1 must not create:

```text
- storyboard prompts
- Seedance prompts
- camera shot plans
- production/editing instructions
```

### Skill 2 — Microdrama Cinematic Director

Responsible for:

```text
- converting approved scripts into 3 video blocks per episode
- shot plans
- storyboard prompts for GPT Image 2
- Seedance 2.0 sound-on video prompts
```

Skill 2 must not create new story concepts from scratch.

### Skill 3 — Microdrama Prompt Packager

Responsible for:

```text
- cleaning and organizing final prompts
- preparing copy-paste-ready prompt packs
- checking prompt completeness
- creating manual production checklists
- organizing outputs into structured Markdown files
```

Skill 3 must not rewrite the story or change creative decisions unless asked.

---

## Core Content Structure

Every story follows this structure:

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
= 1 Seedance video prompt
```

Full story output:

```text
1 Story
= 3 Episodes
= 9 Storyboard Prompts
= 9 Seedance Prompts
```

---

## Episode Structure

Use this default story structure:

```text
Episode 1 = Hook + Humiliation
Episode 2 = Conflict + Mystery
Episode 3 = Reveal + Revenge + Payoff
```

Episode 1 should create curiosity.

Episode 2 should increase emotional tension.

Episode 3 should deliver reveal, revenge, and emotional satisfaction.

---

## Output Folder Structure

Use this output structure for generated files:

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

Definitions:

```text
DRAMA_001 = one main story idea / one story title
EP_001_01 = Episode 1 / Shorts 1
EP_001_02 = Episode 2 / Shorts 2
EP_001_03 = Episode 3 / Shorts 3
```

For the second story, use:

```text
DRAMA_002/
```

---

## Manual-Only Rule

This repo is for manual prompt production only.

Do not create or assume:

```text
- SQLite database
- memory manager
- API integration
- Bumi Digital calls
- OpenAI API calls
- Seedance API calls
- FFmpeg automation
- YouTube upload automation
- background jobs
```

If the user asks for automation, explain that this manual plugin only prepares prompt packs and can be extended later.

---

## Story Style Rules

Stories should feel like fast-paced Asian/Chinese-style vertical microdramas adapted for Indonesian viewers.

Prioritize:

```text
- strong hook
- public humiliation
- emotional injustice
- mystery
- hidden identity
- revenge
- payoff
- cliffhanger
```

Use familiar but addictive tropes:

```text
- hidden heiress
- fake poor billionaire
- secret CEO
- public humiliation
- toxic mother-in-law
- arrogant rich family
- contract marriage
- cheating revenge
- inheritance battle
- fake identity
- poor girl secretly owns the company
- underestimated delivery guy
- ex regrets everything
```

Use this balance:

```text
80% familiar trope
20% fresh twist
```

---

## Script Rules

Scripts must be:

```text
- Bahasa Indonesia
- short
- dramatic
- subtitle-friendly
- fast-paced
- emotionally clear
- easy to understand
```

Avoid long exposition.

Dialogue must be short and sharp.

Good style:

```text
“Kamu pikir wanita miskin seperti dia pantas masuk keluarga kami?”
```

Bad style:

```text
“Sejujurnya aku merasa bahwa situasi sosial yang sedang terjadi ini cukup kompleks...”
```

---

## Character Rules

Character design in this manual workflow has two layers:

### Story Character Layer

Created by Skill 1.

Includes:

```text
- name
- role
- archetype
- personality
- motivation
- weakness
- secret
- emotional function
- relationship dynamics
```

### Visual Character Layer

Prepared for GPT Image 2 character sheet generation.

Includes:

```text
- appearance
- age range
- outfit
- hairstyle
- facial expression style
- body language
- visual identity notes
```

Character sheet prompts should be written in English and should produce consistent reference images for later storyboard prompts.

---

## Shot Plan Rules

Skill 2 must split each 45-second episode into:

```text
Block A = 0–15s
Block B = 15–30s
Block C = 30–45s
```

Default per block:

```text
5 shots × 3 seconds
```

Optional:

```text
6 shots if B-roll is needed
```

B-roll rules:

```text
- maximum 2 B-roll shots per block
- B-roll must support pacing, not slow it down
- total block duration must remain 15 seconds
```

Each shot should include:

```text
- shot number
- duration
- shot type
- visual action
- emotional purpose
- character focus
```

Camera direction can be included only when useful for the prompt.

---

## Storyboard Prompt Rules

Storyboard prompts are for GPT Image 2.

They must be written in English.

Each storyboard prompt must include:

```text
- character sheet reference instruction
- exact panel count based on shot count
- chronological visual progression
- vertical 9:16
- cinematic realistic film-frame collage
- realistic Asian microdrama style
- emotional close-ups
- no comic style
- no manga style
- no cartoon style
- no speech bubbles
```

Panel count rule:

```text
number of panels = number of shots
```

Storyboard prompts should be clear enough that each panel corresponds to one shot in the shot plan.

---

## Seedance Prompt Rules

Seedance prompts must be written in English unless the user requests otherwise.

Each Seedance prompt must include:

```text
- duration: 15 seconds
- aspect ratio: vertical 9:16
- image-to-video instruction
- storyboard image as primary visual reference
- sound-on instruction
- Indonesian dialogue or narration
- ambience
- music mood
- action-synced SFX if needed
```

Do not create separate voiceover instructions outside Seedance.

By default:

```text
dialogue, narration, music, ambience, and SFX should be included directly in the Seedance prompt
```

Seedance prompts should focus on:

```text
- timing
- motion
- acting
- transitions
- audio direction
- emotional pacing
```

Do not overload Seedance prompts with unnecessary long style descriptions if the storyboard image already provides the visual style.

---

## Prompt Packaging Rules

The final prompt pack should be clean and copy-paste-ready.

It should include:

```text
- story concept
- character sheet prompts
- episode scripts
- shot plans
- storyboard prompts
- Seedance prompts
- manual review checklist
```

Do not include unnecessary explanations in final prompt packs.

Use clean headings and separators.

When packaging, preserve the separation between:

```text
- story content
- visual prompts
- video prompts
- review notes
```

---

## Review Checklist Rules

For storyboard review, check:

```text
- character consistency
- outfit consistency
- panel count
- shot accuracy
- emotional clarity
- visual style
- no unwanted text
- no manga/comic/cartoon look
```

For Seedance video review, check:

```text
- duration around 15 seconds
- vertical 9:16
- character consistency
- natural motion
- clear emotion
- dialogue/narration audible
- audio fits the scene
- no major deformity
- ending connects to next block
```

---

## File Writing Rules

When asked to create files, write Markdown files in the output structure.

Prefer one clear file per stage.

Do not overwrite existing files unless the user asks.

If revising, either update the relevant file or create a versioned copy when appropriate.

Suggested versioning:

```text
script_v2.md
storyboard_prompts_v2.md
seedance_prompts_v2.md
prompt_pack_final_v2.md
```

---

## Response Style

Be direct and practical.

Do not over-explain.

When producing content, produce the content.

When giving instructions, keep them structured and actionable.

Always maintain the separation of responsibilities between Skill 1, Skill 2, and Skill 3.

---

## Final Workflow Goal

This project exists to help the user create a complete manual prompt pack for AI microdrama production.

The final goal is:

```text
1 story idea
→ 3 episode scripts
→ 9 storyboard prompts
→ 9 Seedance prompts
→ 1 clean final prompt pack
```

The final prompt pack should allow the user to manually generate:

```text
- character sheet images using GPT Image 2
- storyboard images using GPT Image 2
- video blocks using Seedance 2.0
```

No automation is required unless the user explicitly asks to extend the project later.

---

## Final Rule

Keep the workflow simple, modular, and manual-first.

The user should always be able to take the generated Markdown files and manually copy-paste the prompts into their preferred AI tools.

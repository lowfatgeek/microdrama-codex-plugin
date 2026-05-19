# Microdrama Codex Plugin

Manual AI microdrama prompt-production workflow for creating vertical microdrama content using:

- GPT Image 2 for character sheets and storyboard images
- Seedance 2.0 sound-on for 15-second video blocks
- Codex Agent Skills for structured prompt creation

This repository is designed for **manual prompt production**, not automated generation.

It helps you create a complete prompt pack for:

```text
1 story idea
→ 3 episode scripts
→ 9 storyboard prompts
→ 9 Seedance prompts
→ 1 clean final prompt pack
```

---

## Core Concept

The workflow follows this structure:

```text
1 Story
= 3 Episodes
= 3 Shorts videos
```

Each episode:

```text
1 Episode
= approximately 45 seconds
= 3 video blocks
```

Each block:

```text
1 Block
= 15 seconds
= 1 storyboard prompt
= 1 Seedance prompt
```

So one complete story produces:

```text
3 episode scripts
9 storyboard prompts
9 Seedance prompts
```

---

## What This Plugin Does

This plugin helps Codex create structured Markdown prompt packs for manual use.

It can help with:

```text
- generating microdrama story ideas
- creating 3-episode story concepts
- writing character psychology
- writing 45-second episode scripts
- converting scripts into cinematic shot plans
- creating GPT Image 2 storyboard prompts
- creating Seedance 2.0 sound-on prompts
- packaging everything into final copy-paste-ready Markdown files
```

---

## What This Plugin Does NOT Do

This plugin does not:

```text
- call GPT Image 2 API
- call Seedance API
- call Bumi Digital API
- generate images directly
- generate videos directly
- run FFmpeg
- edit videos
- upload to YouTube
- use SQLite database
- manage production automation
```

It only prepares manual prompt assets.

---

## Skills Included

This plugin contains 3 skills.

### Skill 1 — Microdrama Story Brain

Folder:

```text
skills/microdrama-story-brain/
```

Purpose:

```text
- story ideas
- 3-episode story concepts
- character psychology
- episode scripts
- handoff package for Skill 2
```

Use this when you need to create the story side of the microdrama.

---

### Skill 2 — Microdrama Cinematic Director

Folder:

```text
skills/microdrama-cinematic-director/
```

Purpose:

```text
- split one 45-second episode into 3 blocks
- create shot plans
- create GPT Image 2 storyboard prompts
- create Seedance 2.0 sound-on prompts
- handoff package for Skill 3
```

Use this after a script from Skill 1 is approved.

---

### Skill 3 — Microdrama Prompt Packager

Folder:

```text
skills/microdrama-prompt-packager/
```

Purpose:

```text
- clean and organize approved materials
- create copy-paste-ready prompt packs
- run QA checklist
- produce final prompt_pack_final.md
```

Use this after the story, scripts, shot plans, storyboard prompts, and Seedance prompts are approved.

---

## Recommended Repository Structure

```text
microdrama-codex-plugin/
├── AGENTS.md
├── README.md
├── skills/
│   ├── microdrama-story-brain/
│   │   ├── SKILL.md
│   │   └── templates/
│   │       ├── story_ideas.md
│   │       ├── story_concept.md
│   │       ├── character_psychology.md
│   │       ├── episode_script.md
│   │       └── handoff_to_cinematic_director.md
│   │
│   ├── microdrama-cinematic-director/
│   │   ├── SKILL.md
│   │   └── templates/
│   │       ├── shot_plan.md
│   │       ├── storyboard_prompt.md
│   │       ├── seedance_prompt.md
│   │       └── handoff_to_prompt_packager.md
│   │
│   └── microdrama-prompt-packager/
│       ├── SKILL.md
│       └── templates/
│           ├── final_prompt_pack.md
│           ├── episode_prompt_pack.md
│           ├── qa_checklist.md
│           ├── manual_production_checklist.md
│           └── missing_items_report.md
│
├── templates/
│   └── drama-output-structure.md
│
├── examples/
│   └── DRAMA_001_sample/
│
└── outputs/
```

---

## Output Structure

Use this structure for generated outputs:

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

For the next story, use:

```text
DRAMA_002/
```

---

## Recommended Workflow

### Step 1 — Generate Story Ideas

Use Skill 1.

Example prompt:

```text
Gunakan Microdrama Story Brain untuk membuat 10 ide cerita microdrama Shorts Indonesia.

Format output:
1. Judul
2. Logline
3. Trope utama
4. Hook type
5. Reveal type
6. Virality score
7. Alasan potensial viral

Jangan buat konsep 3 episode dulu sebelum saya memilih ide.
```

---

### Step 2 — Create 3-Episode Story Concept

Use Skill 1.

Example prompt:

```text
Saya pilih ide nomor 3.

Buat konsep cerita lengkap 3 episode.

Struktur:
Episode 1 = Hook + Humiliation
Episode 2 = Conflict + Mystery
Episode 3 = Reveal + Revenge + Payoff

Jangan buat script dulu. Buat beat-by-beat concept dulu untuk saya review.
```

---

### Step 3 — Create Character Psychology

Use Skill 1.

Example prompt:

```text
Buat character psychology untuk cerita ini.

Untuk setiap karakter utama, tampilkan:
- name
- role
- archetype
- personality
- motivation
- weakness
- secret
- emotional function
- relationship dynamics
- basic visual notes

Jangan buat image prompt dulu.
```

---

### Step 4 — Create Episode Scripts

Use Skill 1.

Example prompt:

```text
Buat full script Episode 1 durasi 45 detik.

Episode 1 = Hook + Humiliation.

Format:
[0–5s]
[5–15s]
[15–30s]
[30–40s]
[40–45s]

Script harus:
- Bahasa Indonesia
- dialog pendek dan dramatis
- subtitle-friendly
- high retention
- ending cliffhanger
```

Repeat for Episode 2 and Episode 3.

---

### Step 5 — Create Shot Plan

Use Skill 2.

Example prompt:

```text
Gunakan Microdrama Cinematic Director untuk membuat shot plan Episode 1.

Bagi episode menjadi:
- Block A: 0–15s
- Block B: 15–30s
- Block C: 30–45s

Setiap block:
- default 5 shots @ 3 detik
- boleh 6 shots jika ada B-roll
- B-roll maksimal 2 per block
- total durasi tiap block harus 15 detik

Tampilkan shot plan text version dulu.
```

---

### Step 6 — Create Storyboard Prompts

Use Skill 2.

Example prompt:

```text
Shot plan Episode 1 sudah oke.

Buat 3 storyboard prompts untuk GPT Image 2:
- Block A
- Block B
- Block C

Setiap prompt wajib:
- English
- vertical 9:16
- cinematic storyboard collage
- realistic Asian microdrama film frames
- jumlah panel sesuai jumlah shots
- gunakan character sheet reference instruction
- no comic style
- no manga style
- no cartoon style
```

---

### Step 7 — Create Seedance Prompts

Use Skill 2.

Example prompt:

```text
Buat 3 Seedance 2.0 sound-on prompts untuk Episode 1:
- Block A
- Block B
- Block C

Prompt harus:
- English
- durasi 15 detik
- vertical 9:16
- image-to-video
- storyboard image sebagai primary visual reference
- sound-on
- dialog/narasi Bahasa Indonesia langsung di prompt
- ambience, music mood, dan SFX jika relevan
- tidak perlu voiceover terpisah
```

---

### Step 8 — Create Final Prompt Pack

Use Skill 3.

Example prompt:

```text
Gunakan Microdrama Prompt Packager untuk membuat final prompt pack.

Package semua material yang sudah approved:
- story concept
- characters
- Episode 1 script, shot plan, storyboard prompts, Seedance prompts
- Episode 2 script, shot plan, storyboard prompts, Seedance prompts
- Episode 3 script, shot plan, storyboard prompts, Seedance prompts

Buat output final:
outputs/DRAMA_001/prompt_pack_final.md
```

---

## Manual Production Flow After Prompt Pack

After `prompt_pack_final.md` is ready:

```text
1. Generate character sheet images using GPT Image 2.
2. Use character sheets as references for storyboard generation.
3. Generate storyboard image Block A, B, C for Episode 1.
4. Use each storyboard image as reference for Seedance.
5. Generate Seedance video Block A, B, C.
6. Review each video block.
7. Combine videos manually in your preferred editor.
8. Repeat for Episode 2 and Episode 3.
```

---

## Prompt Language Rules

Story, script, and notes:

```text
Bahasa Indonesia
```

Image/video prompts:

```text
English
```

Indonesian dialogue or narration inside Seedance prompts:

```text
Keep in Bahasa Indonesia
```

---

## Story Style

Stories should feel like:

```text
fast-paced Asian/Chinese-style vertical microdrama adapted for Indonesian viewers
```

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

Use this balance:

```text
80% familiar trope
20% fresh twist
```

---

## Shot Plan Rules

Each episode:

```text
45 seconds
= 3 blocks
```

Each block:

```text
15 seconds
= 5 shots by default
```

Optional:

```text
6 shots if B-roll is needed
```

B-roll rules:

```text
- maximum 2 B-roll shots per block
- B-roll must support pacing
- total block duration must remain 15 seconds
```

---

## Storyboard Prompt Rules

Each storyboard prompt must include:

```text
- vertical 9:16
- cinematic storyboard collage
- realistic Asian microdrama style
- panel count based on shot count
- character sheet reference instruction
- chronological visual progression
- no comic style
- no manga style
- no cartoon style
- no speech bubbles
```

---

## Seedance Prompt Rules

Each Seedance prompt must include:

```text
- duration: 15 seconds
- aspect ratio: vertical 9:16
- mode: image-to-video
- audio: sound-on
- storyboard image as primary visual reference
- Indonesian dialogue/narration when needed
- ambience/music/SFX instructions when relevant
```

Do not create separate voiceover by default.

---

## QA Checklist

Before final packaging, check:

```text
- 1 story has 3 episodes
- each episode has a script
- each episode has 3 blocks
- each block has a storyboard prompt
- each block has a Seedance prompt
- storyboard panel count matches shot count
- Seedance prompt is 15 seconds
- Seedance prompt is vertical 9:16
- Seedance prompt is sound-on
- final prompt pack is clean and copy-paste-ready
```

---

## Notes

This plugin is intentionally manual-first.

Automation such as API calls, database memory, FFmpeg, video editing, or publishing can be added later, but is not part of this repo by default.

# Microdrama Production Workflow

This repository is a manual-first prompt-production workflow for vertical Indonesian microdramas. It creates Markdown prompt packs only; it does not call APIs, generate media, edit video, or publish content.

## Workflow and ownership

```text
Story Brain → Character Sheet Designer → Cinematic Director → Prompt Packager
```

| Skill | Owns | Must not do |
| --- | --- | --- |
| Microdrama Story Brain | Story ideas, 3-episode concept, character psychology, scripts, story handoff | Image/video prompts, shot plans, production instructions |
| Microdrama Character Sheet Designer | Character bible, GPT Image 2.5 character-sheet prompts, character-reference review | Story rewrites, storyboard/video prompts |
| Microdrama Cinematic Director | Model-aware generation plan, shot plan, storyboard and Seedance prompts | New story concepts, character identity redesign, final packaging |
| Microdrama Prompt Packager | QA and copy-paste-ready final pack | Inventing missing creative or visual material |

Story, dialogue, and user-facing notes use Bahasa Indonesia. Image and video prompts use English; spoken dialogue or narration inside video prompts remains Bahasa Indonesia.

## Story contract

```text
1 story = 3 episodes = 3 vertical Shorts
1 episode = approximately 45 seconds
Episode 1 = Hook + Humiliation
Episode 2 = Conflict + Mystery
Episode 3 = Reveal + Revenge + Payoff
```

Prioritize a strong hook, emotional injustice, mystery, hidden identity, satisfying payoff, and subtitle-friendly dialogue. Use familiar Indonesian-adapted Asian microdrama tropes with a fresh twist. Do not add visual instructions to story scripts.

## Production profiles

The episode duration remains approximately 45 seconds. A **generation unit** is one video generation request; it is distinct from a story beat.

| Profile | Video model | Generation plan for a 45s episode | Use when |
| --- | --- | --- | --- |
| `legacy-15s` | Seedance 2.0 | 15s + 15s + 15s | Compatibility or granular iteration is required |
| `controlled-15s` | Seedance 2.5 | 15s + 15s + 15s | User wants Seedance 2.5 but maximum control per scene |
| `long-form-30s` | Seedance 2.5 | 30s + 15s | A contiguous scene benefits from longer acting, motion, and audio continuity |

Never assume arbitrary durations are supported. Use 15-second and 30-second plans only. If no profile is supplied, ask which model/profile the user wants; default to `legacy-15s` only when compatibility is more important than longer takes.

For a 30-second unit, plan timed internal beats (normally 0–10s, 10–20s, 20–30s) and a sequence board whose panel count matches the planned shots. Do not merely concatenate two unrelated 15-second blocks. Preserve continuity into the next unit: identity, wardrobe, location, emotional state, audio bed, and ending pose/action.

## Character-reference contract

Character psychology is not a character sheet. Before storyboard work, Character Sheet Designer creates and the user manually generates one approved GPT Image 2.5 reference image per recurring main character.

Each character sheet prompt must establish:

- face and age range;
- hair, wardrobe, accessories, and body proportions;
- full-body view plus useful expression/angle coverage;
- visual identity lock and exclusions (no text, watermark, duplicate subject, or unapproved wardrobe);
- the approved reference image filename or placeholder.

Storyboard prompts must name the approved sheets that the user should attach. A character description may be used only as a temporary fallback when an image is not available, and the output must explicitly flag that continuity risk.

## Output layout

```text
outputs/
└── DRAMA_001/
    ├── 00_story_concept.md
    ├── 01_characters.md
    ├── 02_character_sheet_prompts.md
    ├── character_sheets/
    │   ├── character_name_reference.png
    │   └── README.md
    ├── EP_001_01/
    │   ├── script.md
    │   ├── generation_plan.md
    │   ├── shot_plan.md
    │   ├── storyboard_prompts.md
    │   └── seedance_prompts.md
    ├── EP_001_02/ ...
    ├── EP_001_03/ ...
    └── prompt_pack_final.md
```

`DRAMA_001` identifies one story. `EP_001_01`, `EP_001_02`, and `EP_001_03` identify its three episodes. Do not overwrite approved files unless asked; use versioned filenames for revisions when appropriate.

## Prompt constraints

### GPT Image 2.5

Use GPT Image 2.5 for character sheets and storyboard/sequence boards. Prompts must be English, vertical 9:16, realistic live-action Asian microdrama frames, with character-reference instructions and no comic, manga, cartoon, speech bubbles, unwanted text, or watermark. The user selects the appropriate GPT Image 2.5 variant and quality in their generation surface; this repository does not make API calls.

### Seedance

Every Seedance prompt must state the selected model/profile, duration, vertical 9:16, image-to-video, sound-on, primary visual reference, timed visual progression, Indonesian dialogue/narration, ambience, music mood, and relevant action-synced SFX. It must not introduce events, characters, locations, or props outside the approved material.

## QA gates

Before packaging, confirm:

- all three episodes and their scripts exist;
- character sheets are generated and approved for recurring main characters, or missing references are clearly reported;
- total duration per episode is approximately 45 seconds;
- every generation unit has a matching storyboard/sequence board and Seedance prompt;
- unit duration matches its selected profile;
- storyboard panel count matches the shot plan;
- character, wardrobe, setting, emotional, and audio continuity hold across units;
- final prompts are complete and copy-paste-ready.

## Manual-only boundary

Do not add databases, APIs, video/image generation calls, FFmpeg, editing, uploads, scheduling, or background jobs unless the user explicitly asks to extend the project beyond this manual workflow.

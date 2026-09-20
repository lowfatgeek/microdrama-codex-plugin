# Microdrama Production Workflow

This repository is a manual-first prompt-production workflow for vertical Indonesian microdramas. It creates Markdown prompt packs only; it does not call APIs, generate media, edit video, or publish content.

## Workflow and ownership

```text
Story Brain → Character Sheet Designer → Cinematic Director → Prompt Packager
```

| Skill | Owns | Must not do |
| --- | --- | --- |
| Microdrama Story Brain | Story ideas, episode-arc plan, character psychology, scripts, story handoff | Image/video prompts, shot plans, production instructions |
| Microdrama Character Sheet Designer | Character bible, GPT Image 2.5 character-sheet prompts, character-reference review | Story rewrites, storyboard/video prompts |
| Microdrama Cinematic Director | Model-aware generation plan, shot plan, storyboard and Seedance prompts | New story concepts, character identity redesign, final packaging |
| Microdrama Prompt Packager | QA and copy-paste-ready final pack | Inventing missing creative or visual material |

Story, dialogue, and user-facing notes use Bahasa Indonesia. Image and video prompts use English; spoken dialogue or narration inside video prompts remains Bahasa Indonesia.

## Story contract

```text
Default: 1 story = 3 episodes = 3 vertical Shorts
Default: 1 episode = approximately 45 seconds
```

The default three-episode arc is Episode 1 = Hook + Humiliation, Episode 2 = Conflict + Mystery, and Episode 3 = Reveal + Revenge + Payoff. It applies only when `episode_count` is 3. For any other count, create an episode-arc plan before scripts: one episode compresses hook-to-payoff; two episodes split escalation and payoff; three or more reserve the first episode for hook/humiliation, the final episode for reveal/payoff, and use the middle episodes for escalation, mystery, reversals, and cliffhangers.

Prioritize a strong hook, emotional injustice, mystery, hidden identity, satisfying payoff, and subtitle-friendly dialogue. Use familiar Indonesian-adapted Asian microdrama tropes with a fresh twist. Do not add visual instructions to story scripts.

## Production profiles

Set a production specification before story or visual work. Defaults are `episode_count: 3` and `default_episode_duration_seconds: 45`. A user may set `episode_count: n`, one new default duration for all episodes, or per-episode duration overrides. A **generation unit** is one video generation request; it is distinct from a story beat.

| Profile | Video model | Default 45s generation plan | Use when |
| --- | --- | --- | --- |
| `legacy-15s` | Seedance 2.0 | 15s + 15s + 15s | Compatibility or granular iteration is required |
| `controlled-15s` | Seedance 2.5 | 15s + 15s + 15s | User wants Seedance 2.5 but maximum control per scene |
| `long-form-30s` | Seedance 2.5 | 30s + 15s | A contiguous scene benefits from longer acting, motion, and audio continuity |

Episode durations must be positive multiples of 15 seconds. Never round a request silently: if a duration is not divisible by 15, ask the user to choose a valid duration or confirm a platform-specific exception. `legacy-15s` and `controlled-15s` use `duration ÷ 15` units. `long-form-30s` uses as many 30-second units as possible and one 15-second unit when needed. If no profile is supplied, ask which model/profile the user wants; default to `legacy-15s` only when compatibility is more important than longer takes.

For a 30-second unit, plan timed internal beats (normally 0–10s, 10–20s, 20–30s) and a sequence board whose panel count matches the planned shots. Do not merely concatenate two unrelated 15-second blocks. Preserve continuity into the next unit: identity, wardrobe, location, emotional state, audio bed, and ending pose/action.

## Character-reference contract

Character psychology is not a character sheet. Before storyboard work, Character Sheet Designer creates and the user manually generates one approved GPT Image 2.5 reference image per recurring main character.

Each character sheet prompt must establish:

- face and age range;
- hair, wardrobe, accessories, and body proportions;
- full-body view plus useful expression/angle coverage;
- visual identity lock and exclusions (only the character-name label as text; no watermark, duplicate subject, or unapproved wardrobe);
- the approved reference image filename or placeholder.

Storyboard prompts must name the approved sheets that the user should attach. A character description may be used only as a temporary fallback when an image is not available, and the output must explicitly flag that continuity risk.

## Output layout

```text
outputs/
└── DRAMA_001/
    ├── production_spec.md
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
    └── EP_001_[NN]/ ...
    └── prompt_pack_final.md
```

`DRAMA_001` identifies one story. `EP_001_01` through `EP_001_[NN]` identify its configured episodes. `production_spec.md` records the requested episode count, every episode duration, video profile, unit plan, and calculated totals. Do not overwrite approved files unless asked; use versioned filenames for revisions when appropriate.

## Prompt constraints

### GPT Image 2.5

Use GPT Image 2.5 for character sheets and storyboard/sequence boards. Prompts must be English, vertical 9:16, realistic live-action Asian microdrama frames, with character-reference instructions and no comic, manga, cartoon, speech bubbles, unwanted text, or watermark. Character sheets must show one clean, correctly spelled character-name label and no other text. Storyboard/sequence boards must show one compact, exact shot time-range label per panel (for example, `0–3s`) and no other text. The user selects the appropriate GPT Image 2.5 variant and quality in their generation surface; this repository does not make API calls.

### Seedance

Every Seedance prompt must use the canonical section order: opening metadata/reference paragraph; `IDENTITY AND VOICE LOCKS`; `SETTING`; `STARTING CONTINUITY`; `TIMED VISUAL PLAN — local clip time`; `DIALOGUE / AUDIO TIMING — Indonesian, preserve every line verbatim`; `AMBIENCE AND MUSIC`; `ACTION-SYNCED SFX`; and `ENDING CONTINUITY`. It must state the selected model/profile, exact duration, vertical 9:16, image-to-video, sound-on, primary visual reference, timed visual progression, Indonesian dialogue/narration, ambience, music mood, relevant action-synced SFX, and continuity constraints. It must not introduce events, characters, locations, or props outside the approved material.

## QA gates

Before packaging, confirm:

- the configured number of episodes and their scripts exist;
- character sheets are generated and approved for recurring main characters, or missing references are clearly reported;
- every episode duration matches its production specification;
- every generation unit has a matching storyboard/sequence board and Seedance prompt;
- unit duration matches its selected profile;
- storyboard panel count matches the shot plan;
- character, wardrobe, setting, emotional, and audio continuity hold across units;
- final prompts are complete and copy-paste-ready.

## Manual-only boundary

Do not add databases, APIs, video/image generation calls, FFmpeg, editing, uploads, scheduling, or background jobs unless the user explicitly asks to extend the project beyond this manual workflow.

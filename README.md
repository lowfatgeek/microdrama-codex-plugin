# Microdrama Codex Skills

Manual-first Codex skills for planning Indonesian vertical microdramas and producing copy-paste-ready prompts for GPT Image 2.5 and Seedance.

```text
Story Brain → Character Sheet Designer → Cinematic Director → Prompt Packager
```

The repository produces Markdown only. Generate images and videos manually in your preferred tools.

## What one story contains

```text
1 story → 3 episodes → approximately 45 seconds each
Episode 1: Hook + Humiliation
Episode 2: Conflict + Mystery
Episode 3: Reveal + Revenge + Payoff
```

## Skills

| Skill | When to use it | Deliverable |
| --- | --- | --- |
| `microdrama-story-brain` | Create or revise story material | Concept, character psychology, episode scripts, handoff |
| `microdrama-character-sheet-designer` | Character psychology is approved | GPT Image 2.5 character-sheet prompts and reference checklist |
| `microdrama-cinematic-director` | Character sheets and a script are ready | Generation plan, shot plan, storyboard prompts, Seedance prompts |
| `microdrama-prompt-packager` | All creative material is approved | QA report and final prompt pack |

## Video profiles

Choose a profile before visual planning:

| Profile | Model | Episode plan |
| --- | --- | --- |
| `legacy-15s` | Seedance 2.0 | 15s + 15s + 15s |
| `controlled-15s` | Seedance 2.5 | 15s + 15s + 15s |
| `long-form-30s` | Seedance 2.5 | 30s + 15s |

Use `long-form-30s` only where the first 30 seconds are a coherent sequence. It has timed internal beats and a sequence board, rather than two unrelated scenes placed together. Use either 15- or 30-second units; do not invent a duration outside the selected model’s documented capability.

## Recommended manual flow

1. Use Story Brain to approve a concept, character psychology, and one episode script at a time.
2. Use Character Sheet Designer to create a GPT Image 2.5 prompt for every recurring main character.
3. Generate and approve the character-sheet images; save them under `character_sheets/`.
4. Use Cinematic Director with the selected Seedance profile and attach the approved character sheets to the storyboard generation.
5. Generate storyboard/sequence boards, then generate each Seedance unit from its matching board.
6. Use Prompt Packager for QA and the final copy-paste pack.

## Output layout

```text
outputs/DRAMA_001/
├── 00_story_concept.md
├── 01_characters.md
├── 02_character_sheet_prompts.md
├── character_sheets/
├── EP_001_01/
│   ├── script.md
│   ├── generation_plan.md
│   ├── shot_plan.md
│   ├── storyboard_prompts.md
│   └── seedance_prompts.md
├── EP_001_02/
├── EP_001_03/
└── prompt_pack_final.md
```

See [`examples/`](examples/README.md) for the sample structure.

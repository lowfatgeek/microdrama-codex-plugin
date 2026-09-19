# Drama Output Structure

Use this layout for a manual microdrama project. All generated text is Markdown; generated images are manually saved as references.

```text
outputs/
└── DRAMA_001/
    ├── production_spec.md
    ├── 00_story_concept.md
    ├── 01_characters.md
    ├── 02_character_sheet_prompts.md
    ├── character_sheets/
    │   ├── README.md
    │   ├── liana_reference.png
    │   └── bu_ratna_reference.png
    ├── EP_001_01/
    │   ├── script.md
    │   ├── generation_plan.md
    │   ├── shot_plan.md
    │   ├── storyboard_prompts.md
    │   └── seedance_prompts.md
    ├── EP_001_02/
    ├── EP_001_03/
    ├── EP_001_[NN]/
    └── prompt_pack_final.md
```

`DRAMA_001` is one story. `EP_001_01` through `EP_001_[NN]` are its configured episodes. `production_spec.md` records episode count, every episode duration, model/profile, generation plan, and calculated prompt totals. The `character_sheets/` directory holds only user-approved visual references; do not treat it as an automated media output.

## Generation plan convention

Every story records a production specification. Its defaults are three 45-second episodes, but users may set a different positive episode count, a different duration for all episodes, or per-episode duration overrides. Durations must be multiples of 15 seconds.

Every episode records one profile:

- `legacy-15s` — Seedance 2.0, one 15-second unit per 15 seconds of episode duration.
- `controlled-15s` — Seedance 2.5, one 15-second unit per 15 seconds of episode duration.
- `long-form-30s` — Seedance 2.5, as many 30-second sequences as possible, then a 15-second sequence if needed.

Each unit has a matching shot plan, storyboard/sequence board, and Seedance prompt. Total storyboard prompts and Seedance prompts each equal the number of generation units across all episodes.

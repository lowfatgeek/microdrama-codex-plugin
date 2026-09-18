# Drama Output Structure

Use this layout for a manual microdrama project. All generated text is Markdown; generated images are manually saved as references.

```text
outputs/
└── DRAMA_001/
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
    └── prompt_pack_final.md
```

`DRAMA_001` is one story. `EP_001_01` through `EP_001_03` are its three episodes. The `character_sheets/` directory holds only the user-approved visual references; do not treat it as an automated media output.

## Generation plan convention

Every episode records one profile:

- `legacy-15s` — Seedance 2.0, three 15-second units.
- `controlled-15s` — Seedance 2.5, three 15-second units.
- `long-form-30s` — Seedance 2.5, a 30-second sequence plus a 15-second sequence.

Each unit has a matching shot plan, storyboard/sequence board, and Seedance prompt. The total episode duration remains approximately 45 seconds.

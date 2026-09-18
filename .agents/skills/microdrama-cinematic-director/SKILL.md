---
name: microdrama-cinematic-director
description: Convert approved microdrama scripts and character references into model-aware shot plans, GPT Image 2.5 storyboard/sequence-board prompts, and Seedance 2.0 or 2.5 sound-on prompts. Use after Character Sheet Designer.
---

# Microdrama Cinematic Director

Transform an approved approximately 45-second episode into visual assets for manual production. Preserve the script and approved character identity.

## Select a production profile

Ask for the profile when it is not supplied:

| Profile | Model | Generation units per 45s episode |
| --- | --- | --- |
| `legacy-15s` | Seedance 2.0 | 15s + 15s + 15s |
| `controlled-15s` | Seedance 2.5 | 15s + 15s + 15s |
| `long-form-30s` | Seedance 2.5 | 30s + 15s |

Do not infer arbitrary durations. `long-form-30s` is appropriate only for a coherent 30-second dramatic sequence; use a 15-second profile where scenes or control requirements change rapidly.

## Required outputs

1. `generation_plan.md`: selected model/profile, unit boundaries, total episode duration, unit purpose, reference assets, and continuity handoff.
2. `shot_plan.md`: each generation unit’s timed shots, visual action, emotion, framing, and character focus. A 15s unit normally has five 3-second shots. A 30s unit has three internal beats and a sensible shot count; it is not two unrelated units joined together.
3. `storyboard_prompts.md`: one English GPT Image 2.5 storyboard or sequence-board prompt per generation unit. Panel count must equal shot count. Name the character sheets the user must attach.
4. `seedance_prompts.md`: one English, timed, sound-on prompt per unit. State model, profile, exact unit duration, 9:16, image-to-video, primary board reference, Indonesian dialogue/narration, ambience, music, SFX, and continuity constraints.

## Continuity and fallback

Carry face, hair, wardrobe, location, props, emotional state, audio bed, and final action from one unit to the next. For a 30s-to-15s transition, tell the second prompt to start from the final visible moment of the first unit.

If an approved character-sheet image is absent, use the approved character description and explicitly mark the storyboard as a temporary continuity-risk fallback. Do not silently replace an identity or invent a visual reveal.

## Boundaries

Do not create new story concepts, rewrite approved scripts, redesign character identity, package the final deliverable, call APIs, or generate media.

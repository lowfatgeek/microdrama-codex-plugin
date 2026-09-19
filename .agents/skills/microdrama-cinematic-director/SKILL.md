---
name: microdrama-cinematic-director
description: Convert approved microdrama scripts and character references into model-aware shot plans, GPT Image 2.5 storyboard/sequence-board prompts, and Seedance 2.0 or 2.5 sound-on prompts. Use after Character Sheet Designer.
---

# Microdrama Cinematic Director

Transform an approved episode of its configured duration into visual assets for manual production. Preserve the script and approved character identity.

## Select a production profile

Ask for the profile when it is not supplied:

| Profile | Model | Unit rule |
| --- | --- | --- |
| `legacy-15s` | Seedance 2.0 | One 15s unit for every 15 seconds of the episode |
| `controlled-15s` | Seedance 2.5 | One 15s unit for every 15 seconds of the episode |
| `long-form-30s` | Seedance 2.5 | Maximize 30s units; use one final 15s unit when required |

Require a positive episode duration divisible by 15. Do not round an unsupported duration. `long-form-30s` is appropriate only for coherent 30-second dramatic sequences; use a 15-second profile where scenes or control requirements change rapidly. Read `production_spec.md` before planning, and calculate units from each episode’s own duration.

## Required outputs

1. `generation_plan.md`: selected model/profile, unit boundaries, total episode duration, unit purpose, reference assets, and continuity handoff.
2. `shot_plan.md`: each generation unit’s timed shots, visual action, emotion, framing, and character focus. A 15s unit normally has five 3-second shots. A 30s unit has three internal beats and a sensible shot count; it is not two unrelated units joined together.
3. `storyboard_prompts.md`: one English GPT Image 2.5 storyboard or sequence-board prompt per generation unit. Panel count must equal shot count. Keep project, episode, and generation-unit metadata outside the image prompt. Within the prompt, identify each character once as `Character: match filename.ext, [visible identity lock]`; do not add a separate collective attachment list or repeat the same filename. Each panel must visibly show its exact shot time range as its only text.
4. `seedance_prompts.md`: one English, timed, sound-on prompt per unit. State model, profile, exact unit duration, 9:16, image-to-video, primary board reference, Indonesian dialogue/narration, ambience, music, SFX, and continuity constraints.

## Continuity and fallback

Carry face, hair, wardrobe, location, props, emotional state, audio bed, and final action from one unit to the next. For a 30s-to-15s transition, tell the second prompt to start from the final visible moment of the first unit.

If an approved character-sheet image is absent, use the approved character description and explicitly mark the storyboard as a temporary continuity-risk fallback. Do not silently replace an identity or invent a visual reveal.

## Boundaries

Do not create new story concepts, rewrite approved scripts, redesign character identity, package the final deliverable, call APIs, or generate media.

---
name: microdrama-character-sheet-designer
description: Turn approved microdrama character psychology into GPT Image 2.5 character-sheet prompts and a reusable visual-continuity reference package. Use after Story Brain and before Cinematic Director; do not write story scripts, storyboards, or video prompts.
---

# Microdrama Character Sheet Designer

Create the visual identity package that makes characters consistent across GPT Image 2.5 storyboard boards and Seedance video generation. This is a manual workflow: produce prompts and review criteria, then ask the user to generate and approve the reference images.

## Inputs and boundaries

Require approved character psychology and basic visual direction. Ask for a missing creative choice only when it prevents a distinct visual identity.

Do not rewrite the story, change a character’s narrative role, create storyboard/Seedance prompts, plan shots, or generate media automatically.

## Deliverables

Create `02_character_sheet_prompts.md` with one English GPT Image 2.5 prompt for every recurring main character. Each entry contains:

- character name, story role, and intended reference filename;
- an identity lock: age range, face, hair, body proportions, wardrobe, accessories, and posture;
- a vertical 9:16 realistic live-action Asian microdrama character-sheet composition, including full body and useful expression/angle coverage;
- an explicit wardrobe/identity continuity instruction;
- exclusions: no text, watermark, duplicate person, unapproved outfit, cartoon, manga, or comic look;
- manual generation and approval checklist.

Use prompt language that is concrete but does not over-specify unapproved story details. Use GPT Image 2.5 as the recommended image model. The user chooses available variant and quality in their image-generation surface.

## Approval gate

The user must generate and approve the reference image before storyboard work. Record the filename or an explicit placeholder under `character_sheets/`. If a sheet is unavailable, pass the approved description as a temporary fallback and flag the resulting continuity risk to Cinematic Director.

## Handoff to Cinematic Director

Provide the approved reference filenames, identity locks, wardrobe state for the episode, characters appearing in each episode, and any unresolved sheet. Do not add camera or video instructions.

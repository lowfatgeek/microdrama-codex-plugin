---
name: microdrama-prompt-packager
description: QA and package approved microdrama story, character-sheet, storyboard, and Seedance materials into a clean manual production pack. Use after Story Brain, Character Sheet Designer, and Cinematic Director; do not invent missing creative material.
---

# Microdrama Prompt Packager

Organize approved materials into clean copy-paste-ready Markdown. Preserve creative decisions and report missing materials instead of inventing them.

## Required package contents

- story concept and character psychology;
- GPT Image 2.5 character-sheet prompts, approved reference filenames, and any missing-reference warning;
- `production_spec.md`, then each configured episode’s script, generation plan, shot plan, storyboard/sequence-board prompts, and Seedance prompts;
- manual production and review checklists.

## Model-aware QA

Validate the production specification and selected profile, not a fixed three-block rule:

- every configured episode exists and has a script;
- every duration is a positive multiple of 15 seconds;
- `legacy-15s` and `controlled-15s`: `duration ÷ 15` units;
- `long-form-30s`: maximum 30-second units and one final 15-second unit if required;
- calculated total prompt count matches the total number of units across all episodes;
- every unit has a matching board and video prompt;
- panel count matches planned shots;
- recurring main characters have approved sheets, or the pack clearly reports the fallback risk;
- prompts preserve character, wardrobe, setting, emotional, and audio continuity.

Prompt text stays in English except Indonesian spoken dialogue/narration. Do not call APIs or generate media.

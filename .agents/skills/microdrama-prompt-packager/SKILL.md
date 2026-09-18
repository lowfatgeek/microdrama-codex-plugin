---
name: microdrama-prompt-packager
description: QA and package approved microdrama story, character-sheet, storyboard, and Seedance materials into a clean manual production pack. Use after Story Brain, Character Sheet Designer, and Cinematic Director; do not invent missing creative material.
---

# Microdrama Prompt Packager

Organize approved materials into clean copy-paste-ready Markdown. Preserve creative decisions and report missing materials instead of inventing them.

## Required package contents

- story concept and character psychology;
- GPT Image 2.5 character-sheet prompts, approved reference filenames, and any missing-reference warning;
- each episode’s script, generation plan, shot plan, storyboard/sequence-board prompts, and Seedance prompts;
- manual production and review checklists.

## Model-aware QA

Validate the selected production profile, not a fixed three-block rule:

- `legacy-15s` and `controlled-15s`: three 15-second units;
- `long-form-30s`: a 30-second unit followed by a 15-second unit;
- total episode duration approximately 45 seconds;
- every unit has a matching board and video prompt;
- panel count matches planned shots;
- recurring main characters have approved sheets, or the pack clearly reports the fallback risk;
- prompts preserve character, wardrobe, setting, emotional, and audio continuity.

Prompt text stays in English except Indonesian spoken dialogue/narration. Do not call APIs or generate media.

---
name: minimax-h3-prompt
description: Create, rewrite, translate, shorten, or troubleshoot MiniMax H3 video prompts for T2VA, I2VA, FL2VA, L2VA, and Ref2VA. Always use for every MiniMax H3 prompt request and follow-up, including requests that only add or revise Japanese dialogue, voiceover, lyrics, or lip-sync lines. Covers Hailuo AI and H3-compatible prompt surfaces. Do not use for MiniMax Hailuo 2.x or unrelated video models unless the user explicitly asks to adapt an H3 prompt.
---

# MiniMax H3 Prompt

Turn the user's intent and supplied media into one copy-ready MiniMax H3 prompt. Preserve the creative direction, make only useful assumptions, and reply in the user's language outside the prompt.

## Route Every Request

1. Identify the input mode:
   - `T2VA`: text only.
   - `I2VA`: supplied first frame.
   - `FL2VA`: supplied first and last frames.
   - `L2VA`: supplied last frame only.
   - `Ref2VA`: one or more reference images, videos, or audio clips used for identity, style, motion, camera, editing, voice, sound, or composition.
2. For `T2VA`, `I2VA`, `FL2VA`, or `L2VA`, read [references/base-modes.md](references/base-modes.md) completely before writing.
3. For `Ref2VA`, read [references/reference-mode.md](references/reference-mode.md) completely before writing. Also read the base guide when shot, camera, dialogue, or sound rules are needed.
4. Whenever the request includes spoken words, singing, voiceover, pronunciation, or lip-sync, read [references/japanese-dialogue.md](references/japanese-dialogue.md) completely. This is mandatory even when the user asks only for a revised line of dialogue in a follow-up.
5. Read [references/sources.md](references/sources.md) only when checking current specifications, reconciling provider differences, or updating this skill.

## Choose the Output Profile

- Use the **official structured profile** by default for MiniMax H3 API, local/open-weight H3 workflows, Context-IR-style prompts, complex references, or requests for the most precise prompt. Keep structural prose in English while preserving dialogue, lyrics, and visible scene text in their intended language.
- Use the **surface-natural profile** when the user explicitly targets a simple Hailuo AI, MiniMax Design, or third-party prompt box and wants a concise natural-language prompt. Keep the same mode, timeline, reference-role, camera, dialogue, and sound logic, but omit schema field names that the surface does not need.
- Do not output both profiles unless the user requests alternatives.

## Resolve Missing Details

Determine the target surface, duration, aspect ratio, input assets and their roles, must-preserve details, action, camera behavior, dialogue, and audio plan from the request. Ask only when a missing choice would materially change the result or a required reference asset is unavailable. Otherwise choose a reasonable draft assumption and state it in one short line before the prompt.

When neither duration nor format is given, use an 8-second, 16:9 draft unless the intended publishing context clearly implies another choice. Keep every cut and action inside the selected duration. Treat resolution, aspect ratio, and provider controls as settings outside the prompt unless they affect composition or timing.

## Write for Observable Playback

- Describe what the viewer can see and hear in chronological order. Replace abstract mood claims with concrete lighting, color, texture, posture, motion, framing, ambience, and sound.
- Use one main subject action and one main camera idea per shot unless the user explicitly requests more. Add a cut only when it reveals new information.
- For image-driven modes, spend prompt space on motion, state changes, and locked details instead of redundantly inventorying the source image.
- Give every reference asset a clear role. Keep labels, speaker IDs, identities, wardrobe, props, product geometry, logos, and spatial relationships consistent.
- Separate synchronized dialogue and diegetic sound from ambience and audience-only music. Use `N/A` for audience-only music when none is wanted.
- Use targeted constraints such as stable horizon, unchanged logo, or no extra people. Avoid long generic negative lists and contradictory directions.
- Do not invent rights or permissions for a real person's likeness or voice. If the request is ambiguous, use fictional subjects or ask for confirmation of the intended authorized reference.

## Japanese Lip-Sync Rules

Apply these rules to every Japanese string that will actually be spoken or sung:

- Replace AI-unfriendly difficult, rare, ambiguous, or irregularly read kanji with hiragana.
- Write numbers with Arabic numerals, never kanji numerals: `2,000年`, `192回`.
- Render spoken English words, abbreviations, and names in katakana according to the intended pronunciation.

Do not alter non-spoken reference tags, URLs, file names, API identifiers, schema keys, timing markers, or exact visible text. Follow the detailed normalization and validation procedure in [references/japanese-dialogue.md](references/japanese-dialogue.md).

## Deliver the Result

Return one clean, copy-ready prompt in a fenced block. Keep assumptions or brief usage notes outside the block. Do not place analysis, citations, or alternative wording inside the prompt. When the user asks only for dialogue, return only the normalized line unless surrounding H3 syntax is necessary for correct use.

Before finishing, verify that the mode is correct, timing fits, every label resolves, keyframes connect through a plausible motion path, camera directions do not conflict, audio layers are separated, and all spoken Japanese passes the lip-sync rules.

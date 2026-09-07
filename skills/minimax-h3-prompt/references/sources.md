# Sources and Authority

Reviewed on 2026-09-07.

Use current official MiniMax documentation and the official model repository as the source of truth. Treat product pages as interface context, third-party guides as practical interpretation, and community posts as anecdotal workflow evidence. When sources conflict, follow the most recent applicable official source and clearly separate provider-specific limits from MiniMax H3 model limits.

## Official Sources

### MiniMax Platform documentation entry

- URL supplied by the user: https://platform.minimaxi.com/document/
- Current documentation area: https://platform.minimaxi.com/docs/guides/video-generation
- Adopted guidance: MiniMax H3 accepts text, first/last-frame images, and multimodal references. The official API identifies the model as `MiniMax-H3`, uses 4–15 second integer durations, supports 768P or 2K, accepts prompts up to 7,000 characters, and limits full-reference inputs by media type. These are time-sensitive API facts; verify them before API-specific advice.

### MiniMax company and H3 research pages

- https://www.minimax.io/
- https://www.minimax.io/blog/minimax-h3
- Adopted guidance: H3 is an omni-modal audio-video model. It jointly models video, dialogue, effects, and music, supports native stereo sound and multi-shot generation, and expresses generalized reference/editing relationships through natural language.

### Hailuo AI product surface

- https://hailuoai.video/
- Adopted guidance: Hailuo AI exposes H3 through a consumer prompt surface with reference-oriented creation. Use the labels and controls visible in the active surface instead of inventing API schema.

### Official MiniMax H3 repository

- https://github.com/MiniMax-AI/MiniMax-H3
- https://github.com/MiniMax-AI/MiniMax-H3/blob/main/skills/h3-prompt-writing/SKILL.md
- https://raw.githubusercontent.com/MiniMax-AI/MiniMax-H3/main/skills/h3-prompt-writing/references/base-en.txt
- https://raw.githubusercontent.com/MiniMax-AI/MiniMax-H3/main/skills/h3-prompt-writing/references/ref-en.txt
- Adopted guidance: five input modes; keyframe alignment; base three-field structure; Ref2VA six-section structure; stable reference and speaker labels; shot timing; camera vocabulary; dialogue markup; and separation of synchronized sound, ambience, and non-diegetic music.

### Official Hugging Face model card

- https://huggingface.co/MiniMaxAI/MiniMax-H3
- https://huggingface.co/MiniMaxAI/MiniMax-H3/blob/main/docs/VIDEO_PROMPT_WRITING_GUIDE_base_en.md
- https://huggingface.co/MiniMaxAI/MiniMax-H3/blob/main/docs/VIDEO_PROMPT_WRITING_GUIDE_ref_en.md
- Adopted guidance: model/input specifications and the canonical prompt-writing guides mirrored by the official repository.

## Supplementary Sources

### Pixo Japanese guide

- https://pixo.video/ja/blog/minimax-h3-prompt-guide
- Useful interpretation: assign every reference a named role; write exact dialogue; describe concrete visible detail; keep on-screen text exact; explicitly disable unwanted music; and identify subjects again across cuts.

### RunDiffusion guide

- https://www.rundiffusion.com/minimax-h3-prompt-guide
- Useful interpretation: order a prompt as visual direction, reference roles, opening, chronological action, camera, dialogue/sound, and ending; use one main camera idea per shot; keep short-clip shot counts realistic; test identity, motion, voice, and cuts in stages. Provider-specific input counts and controls are not universal H3 limits.

### DomoAI image-to-video guide

- https://domoai.app/blog/minimax-h3-image-to-video-guide
- Useful interpretation: start with a coherent source frame; prompt motion rather than re-describing the image; use a plausible path between endpoints; protect only critical details; and review the beginning, middle, end, audio, identity, text, and logos separately. Provider-specific controls are not universal H3 limits.

### Reddit community example

- https://www.reddit.com/r/StableDiffusion/comments/1w8q481/coffee_trying_to_get_cinematic_edits_out_of/
- Anecdotal observation only: one creator reports iterative enhancement, softer grading, detail repair, and reuse of a clean voice-reference file. Do not turn specific LoRA weights, durations, or one user's workflow into default prompt rules.

## Maintenance Rule

Re-check official documentation before changing model names, limits, API fields, supported modes, or provider availability. Preserve the user's permanent Japanese lip-sync preferences even if upstream examples keep dialogue verbatim.

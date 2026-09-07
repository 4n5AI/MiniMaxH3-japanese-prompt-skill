# Full-Reference Mode: Ref2VA

Use this guide when MiniMax H3 combines reference images, videos, or audio for reusable subjects, style, motion, camera, editing, continuation, voice, sound, pacing, or composition.

## Assign One Clear Role per Reference

Inventory every supplied asset before writing. State exactly what each asset controls and what it must not control. One asset may supply several related cues, but name each role explicitly.

Use stable labels:

| Label | Use |
| --- | --- |
| `<Subject N>` | Reusable visible content abstracted from one or more assets: person, object, scene, outfit, style, action, pose, or effect. |
| `<Picture N>` | A concrete target frame, composition anchor, or storyboard/shot-planning image. |
| `<Video N>` | A source video for editing, continuation, or whole-video temporal structure. |
| `<Audio N>` | A copied or referenced audio signal, voice, music style, beat, or sound texture. |

Images and videos that merely define a subject should be cited inside that `<Subject N>` definition rather than receiving redundant standalone labels. Number picture, video, and audio categories independently. Keep each label's meaning unchanged throughout the prompt.

Remove or flag conflicting references. Two incompatible identities, outfits, labels, camera paths, or lighting directions create ambiguity that prose alone cannot reliably solve.

## Official Six-Section Profile

Write all six sections in this exact order:

```text
subject_definitions:
...

summary:
...

retention_analysis:
...

detailed_description:
...

overall_soundscape:
...

non_diegetic_music:
...
```

Keep structural prose in English. Preserve dialogue, lyrics, and visible scene text in their intended language. For Japanese speech, always apply [japanese-dialogue.md](japanese-dialogue.md).

## `subject_definitions`

Give each tracked item one line. Define what it is, where it comes from, its role, and the features that matter. Describe only features needed for consistency; do not create an exhaustive visual inventory.

When an image is a storyboard, map it to specific shots and state that it controls shot order, viewpoint, subject placement, or approximate framing rather than final rendering style unless the user says otherwise.

When reference audio controls a target speaker, connect it to that speaker's stable `(Sx)` ID. Distinguish copying the signal from borrowing timbre or delivery.

## `summary`

Begin with the applicable bracketed task types, joined with ` + ` and without duplicates:

- `keyframe completion`
- `reference generation`
- `video editing`
- `video continuation`
- `audio reuse`
- `audio reference`

Then summarize the target video and main reference relationships in one short paragraph. Do not introduce new labels here.

## `retention_analysis`

Use one line per tracked reference and name where it appears. For visible content, use only:

- `fully_preserved`
- `partially_preserved`
- `attribute_transfer`
- `weak_reference`

For audio, use only:

- `fully_copy`
- `partially_copy`
- `reference`
- `weak_reference`

Explain the retained, changed, transferred, copied, or loosely borrowed properties after the marker. Do not claim full preservation when the target intentionally changes a defined feature.

## `detailed_description`

State the overall visual style in one or two sentences before `[Shot 1]`. Then describe playback order shot by shot: composition, subject appearance and position, environment, lighting, physical actions and state changes, camera movement, synchronized sound, dialogue, and the exact point where each reference takes effect.

For reference-generation tasks, 350–500 English words is a useful planning range, not a quota. Dialogue-heavy or simple edit tasks should use the length needed to make timing and relationships unambiguous. Never pad the prompt with repeated quality adjectives.

Do not timestamp `[Shot 1]`. Give each later shot a strictly increasing cut time within the selected duration. Use a realistic shot count; short clips usually work best with one continuous shot or a small number of purposeful cuts.

## Audio Sections

Keep synchronized dialogue, singing, diegetic music, and event sounds in `detailed_description` beside the corresponding action.

- `overall_soundscape`: ambience, physical sounds, and non-verbal human sounds across the video. If reference audio supplies this layer, state whether it is copied or only referenced.
- `non_diegetic_music`: audience-only score described by instrumentation, tempo, rhythm, and dynamics. Use `N/A` if absent. Do not place audible in-scene music here.

## Surface-Natural Profile

For a simple prompt box, flatten the six-section analysis into a concise brief while retaining its decisions:

```text
visual direction -> reference roles -> retained/transferred features -> chronological shots and camera -> exact dialogue and synchronized sound -> ambience/music -> final composition -> targeted constraints
```

Use exactly the asset labels shown by that surface. Explicitly state identity, style, motion, camera, voice, sound, and storyboard roles so H3 does not have to guess.

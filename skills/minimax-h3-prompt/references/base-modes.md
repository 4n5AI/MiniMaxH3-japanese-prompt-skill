# Base Modes: T2VA, I2VA, FL2VA, L2VA

Use this guide for text-only and first/last-frame MiniMax H3 prompts.

## Select the Mode

| Mode | Inputs | Prompting objective |
| --- | --- | --- |
| `T2VA` | Text only | Construct the complete audiovisual timeline. |
| `I2VA` | First frame | Anchor the exact opening, then describe how motion develops. |
| `FL2VA` | First and last frames | Describe one continuous, physically plausible path between both anchors. |
| `L2VA` | Last frame | Infer a plausible opening and converge precisely on the supplied ending. |

Do not treat a character/style reference as a literal keyframe. When media guides identity, style, motion, camera, voice, or sound without being an exact first or last frame, route to `Ref2VA`.

## Official Structured Profile

For `T2VA`, output these fields in this order:

```text
integrated_multimodal_description: [Shot 1] ...

overall_soundscape: ...

non_diegetic_music: ...
```

For a keyframe mode, put one reference-alignment line before the three fields:

- `I2VA`: state that `<Picture 1>` is the exact first frame of `[Shot 1]` at `0.00` seconds.
- `FL2VA`: map the opening picture to `0.00` seconds and the ending picture to the exact selected duration written with two decimal places.
- `L2VA`: map `<Picture 1>` to the exact final moment and identify the actual final shot number.

Leave one blank line between the alignment instruction and the core fields. Keep picture labels and shot numbers identical throughout.

## Build the Timeline

At the start of `[Shot 1]`, establish the visual medium, composition, subjects, environment, lighting, and initial state. Do not timestamp the first shot. Start each later shot with a strictly increasing cut time inside the selected duration, for example:

```text
[Shot 2] At 00:03.500, the camera cuts to a close-up of ...
```

Describe visible actions as an ordered physical sequence. Include the ending pose, composition, or state so the clip does not stop mid-action.

### I2VA

Use this progression:

```text
exact first-frame anchor -> action onset -> continuous development -> stable result or reaction
```

Preserve identity, clothing, colors, key objects, lighting direction, and spatial relationships that should remain locked. Describe new motion rather than repeating every visible detail.

### FL2VA

Prefer one continuous shot unless the user explicitly requests cuts. Describe intermediate changes that make the endpoint reachable:

```text
opening state -> action begins -> observable intermediate changes -> differences narrow -> exact final state
```

Flag endpoint pairings that cannot connect through the requested continuous action. Offer an intentional transformation, cut, or revised path consistent with the user's intent rather than concealing the discontinuity.

### L2VA

Treat the supplied image only as the required ending. Infer an earlier state compatible with the user's intent, then progressively align the subject, object states, camera, lighting, and composition to the final frame.

## Camera Direction

Express camera movement as a natural action inside the shot. Choose from movements such as push in, pull out, pan, tilt, truck, pedestal, arc, tracking, static, POV, roll, or controlled shake. Add speed and amplitude only when meaningful.

Use a coherent camera path with compatible framing and focus instructions. A locked-off shot cannot simultaneously be a handheld orbit; a dolly zoom intentionally combines camera travel and opposing optical zoom. Distinguish rotation from translation, framing from movement, and camera speed from subject speed. For technique selection and conflict checks, read [cinematography.md](cinematography.md).

## Dialogue and Synchronized Sound

Assign stable speaker IDs such as `(S1)` and `(S2)` in order of first actual vocalization, not visual appearance. Define a speaker clearly at first vocalization and keep the ID across shots. Simultaneous group speech may use a compound ID such as `(S1,S2)`; do not renumber at cuts.

Put only the spoken words and language tag inside `<d>`:

```text
The woman with a low, calm voice (S1) physically speaks with natural lip movement: <d>[Japanese] ...</d>
```

For off-screen narration, use `says in an off-screen voiceover` and immediately after each dialogue block state that the corresponding visible character's lips remain closed. If a line crosses a cut, use `<scenetrans>` at both connecting dialogue boundaries and explicitly continue the same audio across the transition. Use `<cutoff>` only for an intentionally truncated ending, never as a way to fit excessive dialogue.

Read [japanese-dialogue.md](japanese-dialogue.md) before writing Japanese speech, lyrics, or voiceover.

## Audio Fields

- `integrated_multimodal_description`: place dialogue, singing, instruments audible in the scene, and synchronized effects beside the action that creates them.
- `overall_soundscape`: summarize ambience, physical action sounds, and non-verbal human sounds in a short paragraph. Do not repeat dialogue or audience-only music here.
- `non_diegetic_music`: describe audience-only music through instrumentation, tempo, rhythm, and dynamics. Use `N/A` when none is requested.

`overall_soundscape: N/A` means complete silence, not merely no background music. Do not pair it with audible dialogue or effects. Preserve requested visible text exactly in double quotation marks, separately from normalized speech.

## Surface-Natural Profile

For a simple Hailuo AI or third-party prompt box, preserve the same logic in concise natural language:

```text
visual direction -> exact reference/keyframe role -> opening state -> chronological action -> coherent camera path per shot -> exact dialogue and sound -> final state -> targeted constraints
```

Use the asset labels shown by the target surface, such as `画像1`, `Image 1`, or `@image1`. Do not mix naming systems.

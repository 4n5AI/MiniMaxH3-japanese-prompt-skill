# Original H3 Examples

These are authored examples of instruction structure, not tested generations. Duration/format lines are settings outside the prompt. Asset descriptions in hypothetical examples must be replaced after inspecting actual user media.

## T2VA: Portrait, Readable Display Text, Japanese Speech

Brief: 8 seconds, 16:9. A cafe presenter shows a card labeled “AI 二千年” and says “AI、二千年。” No music.

```text
integrated_multimodal_description: [Shot 1] Live-action cafe portrait. An eye-level, locked-off chest-up composition with an 85mm-equivalent short-telephoto look separates the presenter from the soft window-lit background. The presenter's face and the card held beside it at the same depth remain sharp. The card reads "AI 二千年" throughout. The presenter with a warm, clear voice (S1) physically speaks with natural lip movement: <d>[Japanese] エーアイ、2,000年。</d> The mouth remains unobstructed during the line, then closes into a small smile. Hold the final composition.

overall_soundscape: Quiet cafe room tone beneath the speech; a light paper rustle as the card settles.

non_diegetic_music: N/A
```

The visible string is unchanged even though it is also spoken. Soft background focus does not blur the required lettering or mouth.

## T2VA: A Coordinated Dolly Zoom

Brief: 6 seconds, 16:9. A silent realization, no music.

```text
integrated_multimodal_description: [Shot 1] Live-action medium close-up of a traveler standing in a long station corridor. The traveler stops and grips the ticket. As the eyes widen, the camera smoothly dollies backward while optically zooming in to hold the traveler's head and shoulders at a nearly constant size. The corridor's background scale changes around the stationary face. Keep the horizon level and focus on the eyes; settle into a still ending. The traveler does not speak.

overall_soundscape: Ventilation hum and a brief dry crinkle from the ticket.

non_diegetic_music: N/A
```

Do not replace the coordinated movement with either a simple pullback or a fixed-position zoom.

## Ref2VA: Storyboard Composition, Not Literal Keyframes

Hypothetical inspected input: one two-panel storyboard showing a courier outside a doorway, then a close view of a sealed parcel. It controls framing/order only. Brief: 8 seconds, 16:9, no speech or music.

```text
subject_definitions:
<Picture 1>: Supplied two-panel storyboard. Panel 1 guides the doorway composition of Shot 1; panel 2 guides the parcel close-up of Shot 2. It does not define exact frames, identity, or sketch rendering style.

summary:
[reference generation] A live-action delivery scene uses <Picture 1> for shot order and approximate framing, ending on the unopened parcel.

retention_analysis:
<Picture 1>: attribute_transfer — transfer panel order and approximate subject placement into Shots 1–2; replace sketch marks with live-action surfaces.

detailed_description:
Naturalistic live-action daylight with soft side illumination.
[Shot 1] A wide doorway composition follows panel 1 of <Picture 1>. The camera slides slowly sideways from behind the doorframe, revealing a courier holding a sealed parcel. Keep the courier's hands and the parcel visible as the courier stops at the threshold.
[Shot 2] At 00:04.000, cut to the parcel composition from panel 2 of <Picture 1>. A locked-off close-focus view shows the paper texture and intact seal as the courier holds the parcel steady. Keep the whole seal sharp and hold the ending.

overall_soundscape:
Footsteps stop at the doorway, followed by a soft paper rustle and quiet outdoor ambience.

non_diegetic_music:
N/A
```

The storyboard reference is not automatically FL2VA or video editing. This simple reference task needs fewer than 350 words.

# Camera and Lens Choices for H3

Choose a setup for what it shows, not for prestige equipment names. These are visual directions for generated video, not claims that H3 simulates a real camera, aperture, sensor, EXIF metadata, or a specific lens exactly.

## Optical Grounding

TAMRON's guides distinguish field of view, focal length, lens classes, and aperture. Shorter focal lengths cover a wider field on the same sensor; longer ones cover a narrower field. A prime has a fixed focal length; a zoom lens can vary it. Wide views suit environments, standard views everyday scenes, and telephoto views distant subjects or selective portraits. Aperture affects light and depth of field.

Use millimeters as approximate **35mm/full-frame-equivalent framing cues** unless the user gives a sensor format. The same actual focal length does not produce the same field of view on every sensor. Do not quote an angle in degrees without specifying sensor/crop and horizontal, vertical, or diagonal measurement. Lens class boundaries are approximate, not universal thresholds.

Sources: [TAMRON: angle of view](https://www.tamron.com/jp/consumer/sp/impression/detail/article-what-is-angle-of-view.html), [TAMRON: focal length and sensor format](https://www.tamron.com/jp/consumer/sp/impression/detail/article-what-is-focal-length.html).

## Scene-to-Lens Decisions

The ranges and prompt clauses below are working creative choices, not model settings or mandatory photographic prescriptions. Pair a number with its desired visible effect; omit numbers when a plain description is clearer.

| Scene / purpose | Starting choice | Original prompt clause and guardrail |
| --- | --- | --- |
| Interior, landscape, geography | Wide, approximately 16–24mm equivalent | `A wide view from the doorway includes the near table and the far windows; straight architectural edges remain straight.` Do not automatically add fisheye distortion. |
| Person within a place, walking dialogue | Moderate wide, approximately 28–35mm equivalent | `Track beside the pair at conversational distance, keeping both faces and their surroundings legible.` Leave leadroom; avoid placing a close face at an extreme edge. |
| Everyday scene, interview with context | Standard, approximately 40–60mm equivalent | `An eye-level waist-up view preserves a natural-looking face and enough background to identify the cafe.` Choose camera distance to suit framing. |
| Intimate portrait or lip-sync | Short telephoto, approximately 85–105mm equivalent | `From a comfortable distance, frame the face and shoulders; eyes and mouth stay sharp against a softly separated background.` Do not blur the mouth for a fashionable shallow-focus look. |
| Distant sport, wildlife, layered city | Telephoto, approximately 135–300mm equivalent | `Observe from across the street, isolating the runner against overlapping distant storefronts.` Define subject tracking and keep useful leadroom. |
| Product lettering, texture, tiny action | Macro/close-focus look; focal length alone is insufficient | `The engraving fills the frame; its entire word remains sharp while a reflection moves across the metal.` Specify readable extent and stable product geometry. |
| Unusual peephole perspective | Fisheye, intentional curved projection | `A doorway peephole view curves the edges while the visitor remains centered.` Use only when distortion serves the scene. |
| Stylized cinematic highlights | Anamorphic-inspired rendering | `Oval background highlights and restrained horizontal flare frame the face without washing out the eyes.` A wide aspect ratio alone does not define an anamorphic look. |

## Perspective, Focus, and Motion Are Separate Controls

- Perspective follows camera position relative to scene depth. For a stronger near/far relationship, bring the viewpoint closer to a foreground element and choose framing that includes depth. For a compressed-looking portrait, move farther away and use a longer focal length to maintain subject size. Do not claim that zooming alone changes perspective from a fixed viewpoint.
- Changing position with a prime changes subject framing and perspective, not the lens's angular field of view. With a zoom lens, specifying its range does not mean the shot must zoom.
- Depth of field depends on more than focal length: aperture, focus distance, format, and viewing conditions matter. Ask directly for which planes must be sharp. Zooming out does not automatically blur the background; a wide lens does not guarantee everything sharp.
- For selective focus, name what remains sharp and what may soften. For deep focus, name the near and far information to preserve. Do not demand razor-thin focus and every depth plane simultaneously.
- For rack focus, establish near and far subjects, transfer sharpness once at a motivated moment, and keep framing stable unless a separate compatible move is intended. Distinguish focus breathing from a requested zoom.
- Slow camera movement is not slow-motion playback. Lens/aperture cues are not shutter-speed or frame-rate commands. Specify motion texture in words when needed; do not invent provider settings.

## Camera Setup and When to Use It

| Setup / viewpoint character | Use | What to write instead of equipment name alone |
| --- | --- | --- |
| Tripod / locked-off | Product geometry, dialogue, spatial choreography | Fixed position and horizon; name any permitted pan or tilt separately. |
| Dolly / slider | Deliberate approach, lateral parallax, controlled reveal | Route, subject distance change, endpoint, smooth acceleration/deceleration. |
| Stabilized walking camera / gimbal-like | Follow a person through space | Smooth path, subject gap, turn behavior, and clearance through openings. |
| Handheld documentary | Human presence or controlled urgency | Small irregular drift or step motion of stated intensity; preserve readable faces. |
| Crane / jib | Rising viewpoint or foreground-to-geography reveal | Height change plus any coordinated tilt; show the final composition. |
| Drone / aerial | Landscape scale or large orbit | Altitude, travel direction, orbit center, and stable horizon. |
| FPV / body-mounted POV | Subjective speed or a route through space | Who/what owns the viewpoint, path, banking intensity, and ending position. |
| Smartphone / surveillance / film-inspired | A specifically requested capture aesthetic | State the desired framing, texture, stabilization, dynamic range, or grain rather than assume all devices share one look. |

Retain a user-requested camera/lens model, but describe the intended result beside it. Do not invent model-specific color science, sensor characteristics, available lens mounts, or exact simulation support. Hardware shopping advice is outside this prompt-writing guide.

## Explain the Choice Briefly

When the user asks for a recommendation or rationale, give the narrative purpose, camera setup, approximate lens choice, and one tradeoff in their language. Example: “口元を見せる会話なので、目線の高さの固定カメラと85mm相当の胸上構図。背景だけを柔らかくし、目と口は鮮明に保ちます。” For prompt-only requests, include only the corresponding visual instructions.

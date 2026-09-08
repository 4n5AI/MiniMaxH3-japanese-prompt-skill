# Cinematography: Intent to Shot Direction

Use this guide for visual prompts and camera revisions. Read [camera-lenses.md](camera-lenses.md) when choosing camera setups, focal lengths, perspective, depth of field, or a lens for a particular scene.

Contents: shot design; seven axes; camera paths; transitions and continuity; complexity checks.

## Design the Shot Before Naming Equipment

Ask what the audience should notice or feel, then describe the visible result. Choose a shot size and viewpoint, the important spatial relationship, and a motivated path or hold. Add optics, light, and timing only where they change that result. Do not fill every axis with a fashionable keyword.

Translate the choice into this flexible shot sentence:

```text
[opening framing and viewpoint] + [subject action] + [camera path, speed, and endpoint] + [focus target] + [light/composition that matters] + [ending state]
```

Keep camera and lens instructions in the shot's visual prose, outside dialogue and reference-retention markers. The seven-axis organization comes from CinematographyStoryboards; the combinations and prompt examples here are original working adaptations, not verified H3 presets.

## Seven Axes and Their Uses

| Axis | Choices | Use and prompt decision |
| --- | --- | --- |
| Shot size / 画面内の大きさ | ECU, CU, MCU, MS, cowboy, full shot, wide/extreme long | Detail clue → eye or object ECU; emotional reaction → face CU; speech → chest-up MCU with mouth clear; gesture → waist-up MS; hands near hips → above-knee cowboy; movement → whole body; location/scale → wide. Specify how small the subject is for an extreme long shot. |
| Angle / 視点 | Eye-level, low, high, bird's-eye/top-down, worm's-eye, POV, OTS, Dutch | Eye-level for a direct encounter; low/high for deliberate power relationships; overhead for spatial layout; ground-level for looming scale; POV for a character's view; over-the-shoulder for an exchange; tilted horizon for unease. These do not prescribe camera travel. |
| Movement / 移動 | Static, pan, tilt, whip pan, dolly, tracking, arc/orbit, crane/jib, stabilized, handheld, aerial, FPV, optical zoom, dolly zoom, crash zoom | Select a path below. Stabilization and mounting describe motion character, not an additional trajectory. |
| Optics / レンズ・焦点 | Wide, standard, telephoto, anamorphic, fisheye, macro, shallow/deep focus, rack focus, flare | Choose the perspective, subject/background relationship, and focus behavior in [camera-lenses.md](camera-lenses.md). A lens name alone is insufficient. |
| Time / 時間 | Slow motion, speed ramp, time-lapse, hyperlapse, reverse, freeze frame, long take | Slow motion exposes action phases; a speed ramp changes playback pace; time-lapse compresses change; hyperlapse adds travel; reverse reverses action; freeze stops image action; a long take preserves continuity. None requires an automatic change to camera speed. |
| Lighting / 光 | Golden/blue hour, backlight/rim, silhouette, high/low key, soft/hard, practical, neon, volumetric, fire/candlelight | State source, direction, softness, and the detail it reveals. Rim light separates edges; silhouette hides interior detail; practical sources motivate visible illumination; volumetric beams require visible atmosphere. Do not combine a hidden face with readable lip-sync. |
| Composition / 構図 | Thirds, center/symmetry, leading lines, frame-within-frame, negative space, foreground layers, headroom/leadroom | State placement and what remains readable. Leave space for movement or requested text; use foreground layers for parallax/reveals. Portrait format may require more vertical rather than lateral separation. |

These categories cover the storyboard site's seven axes without treating every entry as a camera movement. A wide shot is subject scale; a wide-angle lens is optics. They are not interchangeable.

## Camera Paths: Name the Start, Change, and End

| Request | H3 direction to specify | Typical use / constraint |
| --- | --- | --- |
| Push in / pull out / fast dolly | Move toward/away from a named subject, from one framing to another; specify a gentle or urgent pace. | Commitment, intimacy, or revealing context; allow depth/parallax changes. |
| Pan / tilt | Rotate left-right or up-down from one named target to another from the same camera position. | Follow a glance or reveal height; not sideways/vertical translation. |
| Truck / pedestal | Translate laterally or vertically while specifying viewing direction and endpoint. | Reveal something behind foreground cover; changing viewpoint differs from pan/tilt. |
| Lead / follow / side tracking | Move ahead facing back, behind facing forward, or alongside the subject; maintain a chosen gap and framing. | Walking, running, travel; coordinated pan may maintain the subject's position. |
| Arc / orbit | Travel around a named center, with a partial arc or explicit angle, direction, radius, and ending side when needed. | Reveal dimensional form or changed relationships. Do not silently turn a small arc into a full revolution. |
| Crane / drone reveal / flyover | Describe altitude change, route, tilt if needed, and final composition. | Establish geography; distinguish rising camera from merely tilting up. |
| Through shot / foreground reveal | Identify a clear opening or foreground obstruction and the destination beyond it. | Reveal a room or subject; avoid an unexplained collision through a solid wall. |
| POV walk / handheld / stabilized tracking | Choose the path first; then define gentle footstep bob, controlled handheld drift, or smooth stabilization. | Immersion, documentary presence, or composed movement. |
| Optical zoom / snap zoom | Keep camera position fixed; narrow/widen the field of view, slowly or abruptly, ending on a named detail. | Reframe or emphasize without translational parallax. |
| Dolly zoom / zolly | Move backward while zooming in, or forward while zooming out, maintaining subject size as background scale changes. | Disorientation; coordinated opposing actions, not a contradiction. |
| Whip pan | Rapidly pan between defined compositions, with brief motion blur and a stable landing. | Abrupt attention shift; if it hides a cut, explicitly mark that cut. |
| Dutch angle / barrel roll | Specify a fixed tilted horizon OR active rotation around the viewing axis. | Unease versus tumbling motion; a static tilt is not a rolling camera. |
| Top-down / worm's-eye tracking | Set overhead/ground-level viewpoint separately from any translation. | Geometry or scale; the angle alone does not imply rotation. |

AIShotStudio provides additional movement vocabulary, but its model-specific examples and branded labels are not H3 control syntax. Use observable descriptions instead of copying brackets or claims of guaranteed execution.

## Transitions, Focus Reveals, and Complex Effects

- A blurred-to-sharp reveal starts defocused and resolves one target. A rack focus transfers sharpness between two named depth planes; neither requires camera travel.
- An extreme macro or cosmic hyper-zoom asks for a large change of scale, not necessarily a physically possible optical zoom. State whether it is a continuous simulated transition or a cut between scales.
- Bullet time separates a moving viewpoint from apparently frozen/slowed action. Hyperlapse accelerates time while the viewpoint travels. An FPV dive needs a route and a stable endpoint. Do not substitute one for another.
- For a speed ramp, say which action is normal, slowed, and accelerated. Preserve dialogue at an intelligible pace unless altered audio is explicitly wanted.
- Treat fast full orbits, moving macro focus, barrel rolls, long through-shots, and extreme scale transitions as complex requests needing generation review, not unsupported or guaranteed features. If execution fails, offer a shorter arc, wider framing, fewer transitions, or separated shots while preserving the user's purpose.

## Storyboard Continuity

For each shot, track the subject's screen position, gaze/travel direction, framing, camera height, focus, lighting direction, action start/end, and cut time. Use a shot table only when requested or when planning a complex sequence; otherwise keep the planning internal and return the prompt.

Maintain intelligible screen direction and eyelines across an exchange; if crossing the action axis intentionally, show a reorienting move or establishing view. A continuous take has no cut timestamps. A supplied storyboard may control layout/order without imposing its sketch style or becoming literal first/last frames. Record that role in Ref2VA.

## Conflict and Playback Check

- Does camera direction specify the camera's frame of reference rather than confuse subject-left with camera-left?
- Are path, angle, stabilization, lens change, focus, and subject motion compatible?
- Does the chosen close-up leave space for the requested action and visible mouth?
- Can the ending composition actually follow the start, especially with fixed keyframes?
- Does shallow focus hide a required logo, face, or second subject? Does an orbit expose an unprovided rear view that must be kept exact?
- Are shot cuts distinct from movement, and do durations allow the move to settle?
- If testing generated footage, inspect start/middle/end, geometry, focus, camera landing, identity, visible text, and spoken audio separately. Change the smallest failing instruction first. Do not report generation success based only on prompt review.

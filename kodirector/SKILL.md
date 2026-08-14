---
name: kodirector
description: "Generate paired storyboard and video prompts for error-contained visual-anchor storyboard sheets. Use for kodirector, image-model-ready production-board storyboard prompts, storyboard-to-video prompts, camera/framing/pose reference panels, cinematic titles, scene-appropriate camera language, clean storyboard sheets, effect/prop separation, character-reference exclusivity, interface-driven scenes, and video handoffs that preserve intended staging without copying storyboard drawing artifacts. Created by x.com/aimikoda"
---

# kodirector Prompt Generator

Create two prompt files for the same scene:

- `prompt_storyboard.txt`: an image-model-ready stylish storyboard sheet prompt that acts as a simplified staging and composition reference for intended camera angle, shot scale, framing, pose, blocking, screen direction, composition, prop/effect placement, and spatial continuity.
- `prompt_video.txt`: a video-model prompt that completes the intended storyboard sequence with motion, timing, audio, final visual style, final character reference detail, and choreography while preserving the intended panel camera and framing. It must not inherit accidental drawing errors from the generated storyboard sheet.

The storyboard sheet is not a compressed video prompt. It is a designed production-board artifact plus silent visual-reference panels. Keep the header visually polished, but keep panel interiors free of annotations, arrows, captions, icons, character reference portraits, model sheets, and extra text.

## Authority And Phases

Use this authority model for every kodirector task:

- Writing phase: build one shared `P##` spine first. `prompt_video.txt` carries the full sequence text with motion, timing, audio, style, and completion detail; `prompt_storyboard.txt` carries final visual panel beats rewritten from the same visible spine.
- Derivation phase: storyboard beats preserve the visible event, P## order, storyboard shot tag, storyboard beat name, camera angle, shot scale, framing, pose, blocking, screen direction, character position, prop/effect state, and visible result. Rewrite each video beat through the Image-Prompt Beat Rewrite Contract below: remove video-only detail, convert camera movement into still camera viewpoint, shot scale, and composition, keep lens behavior out of panel body lines, and make each line a drawable single-frame image instruction.
- Generation phase: the generated storyboard image referenced as `@image1` becomes the final video's layout anchor for intended shot order, camera, framing, pose, blocking, screen direction, composition, and spatial continuity. The video text and mapped references remain the authority for final character anatomy, object identity, prop design, effect behavior, motion, audio, final style, timing, and the same P## sequence.

## Defaults

- Output language: English unless the user requests another language.
- Aspect ratio: 16:9.
- File output: save exactly two files inside `kd_prompts/<short_slug>/`: `prompt_video.txt` and `prompt_storyboard.txt`.
- Final response: return only the saved file paths and a short confirmation unless the user explicitly asks to print prompts.
- Storyboard sheet: modern-minimal cinematic production board with an artistic header, panel header strips, and AUTO panel grid.
- Header text: only an evocative cinematic title line and micro-brief line as exact quoted text; do not render field labels, meta line, priority line, tables, extra project fields, reference thumbnails, portraits, model sheets, or prop boxes.
- Panel interiors: silent ultra-clean blocking thumbnails that preserve usable video reference for camera angle, shot scale, composition, body pose, object state, and screen direction while staying deliberately sparse and schematic.
- Storyboard color isolation: keep panel interiors monochrome even when the final video has colored light, colored energy, colored props, or colored characters. Put final color and palette detail in `prompt_video.txt`, not in storyboard panel headers, panel body lines, continuity/count locks, reference roles, or header micro-brief unless the user explicitly requests a colored storyboard sheet.
- Prompt length discipline: write compact, clear prompts from the first draft. Avoid filler, repeated rules, ornamental phrasing, long synonym lists, and restating constraints that are already covered by the template.
- Video prompt: target 3500 characters or less; it may exceed that by up to 10% only when needed for handoff clarity, action cause-effect, prop continuity, camera/panel alignment, or references. Absolute maximum: 3850 characters.
- Storyboard prompt: target 5000 characters or less; it may exceed that by up to 10% only when needed for still-panel art-direction clarity, reference roles, count/entity locks, continuity, or panel count. Absolute maximum: 5500 characters.

## Storyboard Error Containment

Use this rule for every paired storyboard-to-video handoff. The storyboard image is an imperfect planning artifact, not final scene truth.

- In `prompt_storyboard.txt`, make panels intentionally sparse so the image model has fewer chances to invent props, symbols, extra limbs, extra bodies, text, facial detail, material detail, effect icons, or before/after copies.
- In `prompt_video.txt`, state that `@image1` controls intended panel order, framing, staging, screen direction, and spatial layout only. Do not let `@image1` override the written video beats, mapped character references, prop descriptions, or effect definitions.
- Explicitly tell the video model to ignore accidental storyboard artifacts: warped anatomy, extra limbs, duplicate silhouettes, wrong text, wrong letters, malformed props, stray marks, arrows, icons, effect scribbles, sketch debris, panel borders, headers, sheet typography, and simplified blocking anatomy.
- When a generated storyboard panel is likely to be visually ambiguous, make the matching video beat name the final real-world object or effect in plain language rather than asking the video model to infer it from the drawing.
- Treat storyboard silhouettes as pose and blocking guides only. Final faces, bodies, wardrobe, materials, textures, creature design, vehicle design, and prop construction come from the video text or mapped references, not from the storyboard drawing.

## Effect And Prop Separation

Use this rule whenever the scene contains magic, aura, smoke, dust, debris, sparks, water spray, motion lines, impact bursts, screens, light beams, UI-like shapes, or any abstract effect mark.

- In `prompt_storyboard.txt`, draw effects as minimal abstract state marks attached to a clear origin: a short trail, contact burst, glow halo outline, dust wedge, spray arc, smoke plume, or impact ring. Keep them open-outline, monochrome, and non-object-like.
- Never describe storyboard effects as standalone objects, creatures, tools, icons, stickers, labels, symbols, or props unless the story truly contains a physical object.
- Name the effect origin and attachment point in every risky panel: from the hand, from the keyboard impact face, from the hoof contact, behind the wheel, around the doorway, along the floor path.
- If a physical prop and an effect appear together, separate them in wording: `the same physical sword remains in the lead figure's hand; one short impact arc touches the blade edge`. Do not let the effect inherit prop language such as held, carried, dropped, collected, or placed.
- In `prompt_video.txt`, restate each important effect as final-video behavior and material logic, so the video model renders it as light, dust, smoke, debris, water, energy, or motion instead of copying a storyboard scribble as a new prop.

## Core Split

Use this division for every kodirector task.

Storyboard visual-anchor layer:

- Camera angle, viewpoint, shot scale, framing, frame composition, and screen direction.
- Character pose, body orientation, gesture, eye-line, and movement direction.
- Character screen position and foreground, midground, and background relation.
- Exact count and identity continuity for count-sensitive characters, bodies, vehicles, weapons, props, repeated state marks, and other countable entities.
- Essential prop placement and simplified effect placement, with effects attached to a visible origin and kept visually separate from physical props.
- Spatial continuity, geography, and layout anchors.
- Simple scene silhouettes needed for the video model to read the board.
- Header and panel headers as sheet design elements only.

Video completion layer:

- Camera movement, lens behavior, timing, and pacing only when they preserve the storyboard panel's camera angle, shot scale, framing, and composition.
- Audio, SFX, ambience, silence, music direction if requested.
- Final video medium, lighting key, color and palette emotion, lens and depth-of-field feel, texture and atmosphere, render style, and motion quality.
- Final character appearance, face, wardrobe, body proportions, material detail, and likeness from mapped references.
- Final physical prop design and final effect rendering, including material, color, light, particles, smoke, dust, debris, energy, water, or impact behavior.
- Detailed choreography and continuity that should not be drawn as text, arrows, diagrams, or annotations in the storyboard.

The video prompt must preserve intended panel camera angles, shot scale, framing, poses, screen positions, prop states, and geography, but must correct accidental storyboard drawing artifacts through explicit written beats and reference mapping.

## Storyboard Color Isolation

Use this rule whenever the final video includes colored energy, colored light, glowing creatures, aura, fire, magic, lasers, blood, branded colors, wardrobe colors, or colored environment details.

- In `prompt_storyboard.txt`, describe colored video elements by color-neutral shape and function. Use shape, placement, scale, outline, trail, mark, silhouette, path, and object-state language rather than color or palette language.
- Do not put any wording that names or implies final color, palette, colored light, color temperature, material color, or saturation in storyboard panel headers, panel body lines, continuity/count locks, reference roles, or the quoted micro-brief when panel interiors must stay monochrome.
- If the video needs the color for final generation, keep it in `prompt_video.txt` `VISUAL STYLE`, `ENVIRONMENT`, or the matching `P##` beat.
- If the storyboard sheet needs graphic treatment, keep it non-color, sheet-level only, and outside panel interiors; do not reuse any final-video color as a sheet or panel instruction.
- For count/entity locks, name the continuing entity without any color or light-color descriptor.

## Storyboard Entity Token Isolation

Use this rule whenever `prompt_storyboard.txt` is written for an image model.

- Use stable entity IDs such as `C1`, `C2`, `S1`, or object IDs only as internal planning labels and, when useful, in `prompt_video.txt`.
- Do not write raw entity ID tokens such as `C1`, `C2`, `C3`, `S1`, `O1`, or similar letter-number labels anywhere in `prompt_storyboard.txt`, except for `P##` panel numbers in panel headers.
- Before saving `prompt_storyboard.txt`, translate internal IDs into natural non-label role names: `lead silhouette`, `opposing silhouette`, `fallen guard`, `same sword`, `same spirit shape`, `same cup`, `rear vehicle`, or another scene-specific role phrase.
- Panel beats, continuity, count locks, and reference roles must use those natural role names and screen positions, not code-like labels. This prevents the image model from drawing labels or annotations inside panels.
- When exact continuity is needed, write it as natural language: `the same lead silhouette`, `the opposing silhouette remains screen right`, `the same sword stays in the lead figure's hand`, or `one spirit shape continues across panels`.

## Shared Sequence Spine

Build one shared `P##` sequence spine before writing either file. Use the same panel count, `P##` order, internal shot tags, internal beat names, core action event, camera angle, shot scale, frame composition, character positions, count/entity state, prop and effect state, and spatial result for both `prompt_storyboard.txt` and `prompt_video.txt`. Print shot tags and beat names only in `prompt_storyboard.txt` panel headers, not in `prompt_video.txt`.

- `prompt_storyboard.txt` rewrites each completed video `P##` beat into a final still-panel image instruction. It is not a pasted copy of the video wording with terms removed. Preserve the same P## order, storyboard shot tag, storyboard beat name, camera angle, shot scale, framing, visible event, pose/blocking, screen direction, character/object positions, count/entity state, prop/effect state, spatial result, and visible result.
- `prompt_video.txt` writes the matching `P##` beat as the same frame and scene event, then adds motion, timing, lens behavior, and final-video completion detail without changing the panel's camera angle or composition. In video `BEATS`, print each beat as `P##:` only; do not include any slash-delimited storyboard shot tag or beat name after the panel number.
- Storyboard beat wording may change sentence structure and visual detail level to improve image-model interpretation: explicit camera angle, shot scale, character placement, object contact, anchor geometry, screen direction, count locks, and one frozen state per panel.
- Convert video camera movement into still storyboard language: camera angle, viewpoint, shot scale, framing, and composition. Do not leave camera-movement terms such as dolly, push-in, orbit, crane, handheld, or chase camera in storyboard panel lines.
- Remove lens tags and lens-behavior terms such as 24mm, 35mm, telephoto, macro, zoom lens, rack focus, or depth-of-field behavior from storyboard panel body lines. Include numeric or named lens tags only in panel headers when the user explicitly requests them.
- Do not summarize a beat into vague prose, rename P## beats, reorder beats, reinterpret the visible event, or add new story events. Rewrite only to make the same visible beat clearer as a drawable image panel.
- Do not invent alternate video beats, combine storyboard panels, split one storyboard panel into multiple video events, rename beats, reorder beats, or change the visible event between the two prompts.
- The storyboard sequence and video `BEATS` must read as the same framed sequence with different model-specific wording, not two different interpretations.

## Image-Prompt Beat Rewrite Contract

Use this contract internally every time `prompt_storyboard.txt` is written. Do not print this contract, cite the source rules, mention a model name, or describe the rewrite process in the final prompt.

Storyboard `BEATS` are not video beats with deletions. They are finished still-image panel instructions produced from the video `BEATS`.

For each completed video `P##` beat:

1. Extract only the visible still-frame payload: `P##`, storyboard shot tag, storyboard beat name, camera angle, shot scale, framing/composition, internal entity/object identities, screen positions, pose, object contact, prop/effect state, exact counts, spatial result, and visible result.
2. Discard video completion payload: audio, SFX, foley, ambience, music, silence, cuts, timing, pacing, camera travel terms, lens behavior, final render style, lighting style, color/hue/palette wording, material finish, cinematic grade, atmosphere, invisible intent, and any choreography that cannot be seen in the selected frame.
3. Choose one drawable instant. If the video beat contains trigger -> movement -> result, keep the most readable single frame, usually the contact/result pose. If both cause and result are required for clarity, split them into separate `P##` beats before finalizing both prompts.
4. Rewrite as direct image art direction, not a prose summary: `camera angle + shot scale + frame composition + exact role/object placement + one pose/state + object contact/effect origin + screen direction + spatial result`.
5. Make counts literal when drift is likely. Enumerate natural role names and positions; name continuing bodies, physical props, marks, trails, reflections, debris, vehicles, doors, or effect origins as the same role/object, not repeated extras. Separate physical props from abstract effect marks in wording.
6. Keep the line compact but complete. Use concrete nouns, spatial words, and visible states. Avoid vague praise, emotional abstraction, hidden motivation, and multi-action wording.
7. The final storyboard prompt must contain only the finished visual beats. It must not say that the beats were copied, converted, rewritten from video, adapted from rules, or made for a named model/product.

Failure condition: if a storyboard panel line can still be used as a video beat without changes, it has not been rewritten enough.

## Video Direction Pass

Before building the shared sequence spine, run this internal director pass. Do not output it as a separate section; fold the decisions into the cinematic title, `prompt_video.txt` `BEATS`, and the short prose rhythm/escalation handoff, then pass each completed video beat through the Image-Prompt Beat Rewrite Contract for the storyboard panel lines.

- Define the sequence intent in one sentence, plus start state, end state, conflict, key prop and effect, and the one visual idea the board must communicate.
- Create a cinematic title: 2-5 words, scene-specific, memorable, and atmospheric. Prefer concrete image plus dramatic pressure, consequence, or irony; avoid literal slug titles, technique labels, generic genre names, and explanatory titles such as "Night Market Kali Flow" unless the user explicitly provided that title.
- Pick one scene-appropriate cinema language: `rain-noir compression`, `kinetic close-quarters action`, `procedural prop-chain escalation`, `developing master`, `immersive tracking long-take`, `suspense reveal`, `slow-burn dread`, `action chase`, `standoff escalation`, `emotional close progression`, `lyrical romantic flow`, `comedic timing coverage`, `montage`, `parallel action`, `static formal symmetry`, `epic scale vista`, `subjective POV immersion`, `surreal shift`, or `simple coverage`.
- Let the chosen cinema language control shot angle pattern, shot scale progression, camera motion or edit rhythm, beat names, and the prose rhythm/escalation handoff. Avoid flat coverage when the scene calls for style.
- Choose shot size by story function: geography, action readability, reaction, detail, reveal, threat, intimacy, scale, or final consequence.
- Treat `camera angle` as dramatic language, not a neutral label. Every panel needs a reason for its viewpoint: pressure, vulnerability, scale, concealment, impact, intimacy, irony, surveillance, ritual order, speed, confusion, or release.
- Avoid generic coverage drift. Do not let a board collapse into repeated `low wide`, `side medium`, `frontal close`, `overhead wide`, or `hero wide` unless those repetitions are the deliberate formal idea. Adjacent panels should normally change at least one meaningful camera dimension: height, axis, distance, foreground obstruction, subject scale, negative space, or geometric emphasis.
- Write shot tags as `viewpoint + dramatic function`, not only `angle + size`. Prefer tags like `low root track / dark advance`, `overhead void / rear absence`, `compressed profile / trap line`, `ground insert / failed grip`, `canted close / realization`, `top-down geometry / encirclement`, `long-lens crush / pursuit`, or `static wide / comic reveal` over plain `low wide`, `side medium`, or `close-up`.
- Add a master geography beat as P01 or P02 for multiple characters, combat, pursuit, vehicles, doors, room transitions, fragile screen direction, or changing geography.
- Write visible action with `trigger + movement + reaction gesture + spatial relation + prop/effect state + visible result`.
- Use one main action per beat; include one readable body detail only when it clarifies emotion, force, direction, or consequence.
- Treat each storyboard panel as one frozen instant. If a beat contains a before/after sequence, split it into separate panels or choose one single readable pose/state; do not write `then`, `after`, `before`, or "state A, then state B" inside a storyboard panel line.
- Convert emotion into visible behavior: posture, distance, eye-line, hand tension, pace, framing, hesitation, recoil, commitment, or stillness.
- Preserve world logic through props and consequences: carried, dropped, broken, opened, blocked, displaced, glowing, damaged, missing, wet, marked, or changed.
- Make every beat advance action, emotion, geography, or consequence. End with impact, reveal, unresolved motion, pursuit, danger, collision, transformation, or changed meaning.
- For normal coverage, use compact edit and rhythm language only when useful: hard cut, cut on action, insert, reaction cut, match cut, smash cut, jump cut, cross-cutting, object pass, or whip pan.
- For continuous, one-shot, or developing-master requests, do not describe cuts. Treat every `P##` as a sampled phase of one physical camera path.
- For continuous boards, use one primary virtual lens by default. If scale changes, explain it as physical camera movement: push-in, pullback, dolly, crane, jib, orbit radius, side track, or hold distance.
- Avoid camera contradictions: unmotivated wide-to-telephoto shifts, push-in followed by unexplained pullback, a new establishing shot when it should be the same layout, or adjacent lens jumps without visible zoom logic.
- Lock continuity only where drift is likely: character ID, silhouette, wardrobe, key prop, screen side, travel direction, set anchors, effect origin, intensity, and trail, camera axis, and allowed changes.
- When final beats return to the same location, state that the wider view is the same layout with more camera distance, not a redesigned establishing shot.
- After the cinema language is set, run the Cinematography Layer to lock one coherent lighting key, color-emotion, lens and depth-of-field feel, and atmosphere for the `VISUAL STYLE` line.

## Dramatic Camera Language

Run this internal pass after choosing the cinema language and before finalizing the shared `P##` spine. The goal is expressive, genre-aware camera language that still remains drawable, stable, and useful as a video anchor.

- Give each panel one primary camera idea: occlusion, negative space, compression, foreground obstruction, scale contrast, surveillance view, subject isolation, reflection, threshold framing, top-down geometry, ground evidence, object POV, silhouette, symmetry, canted imbalance, or impact proximity.
- Match camera ideas to genre and scene pressure. Horror and suspense favor occlusion, empty space, surveillance angles, ground evidence, and withheld threat; action favors low impact angles, diagonals, parallax layers, body vectors, and readable collision lines; martial-arts and dance favor full-body clarity, pose geometry, arc paths, and rhythm changes; romance favors distance, eyeline, shared negative space, and soft barriers; comedy favors static reveals, clean wide timing, and object irony; epic scale favors tiny figures against large architecture, sky, crowd, or terrain; ritual/formal scenes favor symmetry, frontal geometry, and measured progression.
- Design the camera progression as a sentence, not a list of coverage. Example patterns: `wide geography -> obstructed approach -> detail evidence -> compressed pressure -> release wide`; `clean master -> kinetic diagonals -> impact insert -> reaction isolation`; `formal symmetry -> small deviation -> broken symmetry -> consequence`.
- If two consecutive panels share the same axis, height, and shot size, keep it only when the story needs a formal match, jump in state, rhythmic repetition, or continuity proof. Otherwise revise one panel.
- Use stronger nouns in shot tags. `void`, `trap`, `witness`, `evidence`, `impact`, `release`, `isolation`, `surveillance`, `threshold`, `pressure`, `scale`, `aftermath`, and `realization` are useful because they name the shot's job.
- Keep expressive camera choices compatible with the storyboard zone contract. In storyboard beats, describe the still viewpoint and composition only; put movement, lens behavior, timing, and edit feel in `prompt_video.txt`.

## Cinematography Layer

Run this compact internal pass for `prompt_video.txt` only, right after the cinema language is set. Fold the result into one tight `VISUAL STYLE` line and never draw it in storyboard panels; panels stay silent, monochrome, and open-outline. Pick one coherent option per dimension so the whole sequence reads as a single emotional look, and let the cinema language steer every choice.

- Lighting key: choose one mood-driven key plus one motivated source, and note contrast and direction in a few words. Options: high-key open, naturalistic motivated, low-key chiaroscuro, hard single-source, soft wrap, silhouette backlight, practical-lit, or firelight/neon/screen glow.
- Color and emotion: choose one palette logic tied to feeling, treating color temperature as emotion rather than decoration: warm-dominant, cool-dominant, warm/cool split, complementary tension, desaturated bleak, monochrome plus one accent, or saturated heightened.
- Lens and focal feel: tie focal length and depth of field to feeling for the final video only. Wide reads as space, isolation, distortion, or immersion; normal reads as grounded realism; long reads as compression, voyeurism, or intimacy. Shallow depth isolates the subject; deep depth holds context. Storyboard panel body lines stay lens-free unless the user requested lens tags.
- Atmosphere and texture: choose at most one unifying atmospheric layer that carries mood, not a pile: haze, rain, smoke, dust, heat shimmer, bloom, fine grain, or clean air.

Coherence rule: lighting, color, lens, and atmosphere must reinforce one emotional read and match the cinema language. For example, rain-noir compression pairs low-key chiaroscuro, a cool neon palette, long-lens compression, and wet haze; comedic timing coverage pairs bright high-key light, a clean warm palette, normal lenses, and clear air. Avoid contradictory looks such as bright high-key comedy lighting on a dread sequence.

## Interface-Driven Scene Clarification

Apply this clarification only when screens, wall displays, control surfaces, governance states, or other interfaces carry important story information. Keep the standard kodirector workflow unchanged for other scenes.

- Treat character masters, environment masters, UI screens, props, and devices as separate image references. The storyboard sheet controls staging and composition only; it is not an asset board or UI design board.
- Keep every screen attached to its established physical wall, display, console, or device. Do not invent floating windows, detached HUDs, or holographic panels unless the scene explicitly requires them.
- Inside storyboard panels, draw only the screen's physical placement and the minimum large state grouping needed to direct attention. Do not reproduce UI copy, governance logic, ownership diagrams, approval tables, flowcharts, or status explanations. Put detailed interface meaning in mapped UI references and `prompt_video.txt`.
- A UI state may justify a new `P##` only when it creates a distinct drawable information-reveal state, composition, reaction pose, or action contact. Do not create panels merely to enumerate text or system facts.
- Frame interface moments as diegetic camera views: a character with the physical screen, an over-shoulder view, a profile with the control surface, or a clean insert of the same anchored display. Never replace a camera view with an infographic.
- For continuous or developing-master scenes, several `P##` panels may be sampled states of one physical camera path. State this explicitly in `prompt_video.txt`; do not interpret those panels as separate cuts.

## Workflow

1. Extract the premise, mood, genre, location, character count, action arc, props and effects, count-sensitive entities, start state, end state, continuity locks, any user-supplied title, and any visual references.
2. Choose the smallest panel count that preserves cause-effect and video-reference poses, usually 3-8 panels unless the user asks for a longer board or the action genuinely needs more. Treat 3-8 as a working range, never a quota. Determine panel count from compositions, spatial-continuity states, camera-transition states, action key poses, and information-reveal states that must be locked; never split panels evenly by elapsed time. Multiple panels may sample the start, transition, and end of one continuous shot and do not imply multiple cuts.
3. Set the storyboard `Grid:` layout to `AUTO` unless the user explicitly specifies a panel layout. Choose the panel count, but let the image model arrange the sheet cleanly.
4. Add a master geography panel as P01 or P02 when the scene has multiple characters, combat, pursuit, vehicles, doors, room transitions, fragile screen direction, or changing geography.
5. Sanitize characters into stable internal IDs for planning, then assign storyboard-safe role names for `prompt_storyboard.txt`. Draw storyboard characters as simple open-outline blocking silhouettes: outer body-mass and limb contours only, with no face detail, clothing detail, texture, or character-design finish.
6. Build a count/entity lock for any duplicate-prone scene: exact visible totals, internal identities, storyboard-safe role names, screen positions, one-instance-only states, and which carried, dropped, fallen, broken, opened, blocked, glowing, damaged, wet, marked, or missing entities persist across panels.
7. Run the Video Direction Pass to choose the cinematic title, scene-specific cinema language, camera grammar, shot functions, rhythm and edit logic, visible action logic, world consequences, and continuity locks.
8. Run the Dramatic Camera Language pass so every shot tag and camera choice has a visible dramatic function, not just a neutral angle/size label.
9. Build the shared `P##` sequence spine: panel count, internal shot tags, internal beat names, core visible action, camera angle, shot scale, composition, pose and blocking, screen direction, prop and effect state, count/entity state, and visible result.
10. Write `prompt_video.txt` from the shared spine, adding only video completion detail around the same P## events.
11. Write `prompt_storyboard.txt` after `prompt_video.txt`; pass every completed video `P##` beat through the Image-Prompt Beat Rewrite Contract before inserting it into `[BEATS]`. Preserve the same P## order, storyboard shot tags, storyboard beat names, camera angle, shot scale, framing, visible action, pose/blocking, prop/effect states, count/entity states, and visible results, while rewriting the wording as finished still-image art direction. Wrap the visual beats in a structured image-prompt format: format sentence, subject/purpose, header, board structure, visual style, optional references, continuity, optional count lock, text rules, constraints, and beats.
12. Run the storyboard color-isolation, entity-token isolation, and effect/prop separation pass: remove final-video color and palette wording from storyboard header micro-brief, panel headers, panel body lines, continuity, count locks, and reference roles unless the user explicitly requested colored storyboard panels. Replace raw entity ID tokens with natural role names everywhere in `prompt_storyboard.txt`. Keep color detail and raw IDs only in `prompt_video.txt` or internal planning. Make every abstract effect mark attached to an origin and clearly non-physical.
13. Before saving, run a compactness pass on both prompts: remove filler, duplicate rules, decorative wording, redundant adjectives, and repeated exclusions while preserving handoff clarity, visible action, prop continuity, count/entity locks, screen direction, camera/panel alignment, and setup/payoff logic.
14. Run the stale-negative pass: remove unnecessary negative statements, obsolete effect tails, and repeated absence notes from panel beats once the global style or continuity rules already cover them. Do not mention vanished, fallen, or transformed entities as active characters in later beats; refer only to their current visible state such as traces, debris, shadows, or absence when needed.
15. If shortening either prompt for length, run the compression safety pass: reread the shortened result and fix any broken action flow, prop pickup/held/dropped/broken/returned continuity, screen-direction drift, camera/panel mismatch, missing setup, or impossible logic jump.
16. Save both files and validate the zone rules, panel-to-video alignment, effect/prop separation, storyboard error containment, continuity, and file lengths.

## Zone Contract

Protect these sheet zones. Prompt section labels are allowed as instruction scaffolding, but they must not be rendered as visible text in the image:

- Header: only the quoted cinematic title line and quoted micro-brief line, with restrained scene-aware typography and graphic treatment. Do not render field labels.
- Panel headers: only compact `P## / shot tag / beat name` text. Do not include numeric lens tags unless the user explicitly asks for lens tags in panel headers.
- Panel interiors: silent visual-reference drawings only. No readable text, arrows, labels, icons, captions, subtitles, speech bubbles, readable UI copy, timing marks, diagrams, legends, technical overlays, character cards, reference portraits, model sheets, wardrobe samples, or inset images. For interface-driven scenes only, an established physical screen may contain a few unlabeled divisions or one large state highlight needed for staging; it must not become a UI design or infographic.

Merge these requirements into the relevant storyboard prompt sections. Do not create visible zone labels, project cards, tables, legends, thumbnails, or extra data fields in the generated sheet.

## Character And Reference Rules

- Use stable IDs internally and in `prompt_video.txt`: `C1`, `C2`, `C3`, etc. for characters, and short stable names for other countable entities when needed. In `prompt_storyboard.txt`, translate those IDs into natural role names and never expose raw entity ID tokens.
- In `prompt_storyboard.txt`, user-supplied references are metadata only. When references exist, include a short `[REFERENCES]` section that assigns each reference a role with `Image A`, `Image B`, and `Image C` labels.
- Reference roles must be explicit and narrow, such as character silhouette and wardrobe block, environment structure, prop shape, lighting direction, or composition. Do not merge unrelated reference roles, and do not include final-video color or palette roles in `prompt_storyboard.txt`.
- Character and wardrobe references are exclusive to the assigned role only. Never let a referenced face, hair, wardrobe, body type, likeness, or material style bleed onto unreferenced bystanders, guards, coworkers, crowds, riders, background figures, opponents, doubles, or new characters unless the user explicitly asks for twins, clones, uniforms, or identical casting.
- When the scene includes referenced and unreferenced people together, give unreferenced roles distinct generic appearance cues in `prompt_video.txt`: different faces, hair masses, wardrobe silhouettes, body proportions, age band, or distance from camera. Include a short no-likeness clause in the single character-reference sentence only in this multi-character case.
- Do not ask the storyboard image model to draw reference portraits, face studies, body studies, wardrobe samples, prop sample boxes, character cards, or model-sheet inserts.
- Storyboard characters are simple open-outline blocking silhouettes: outer body-mass and limb contours only, with no internal anatomy, face detail, clothing detail, fabric detail, material texture, portrait treatment, or model-sheet treatment. Use references only for gross height, body mass, hair block, and wardrobe block.
- In `prompt_video.txt`, reserve `@image1` for the generated storyboard sheet.
- Internally map storyboard metadata labels to video asset tags after the storyboard image: Image A becomes `@image2`, Image B becomes `@image3`, and Image C becomes `@image4`. This mapping is for generation only.
- In `prompt_video.txt`, never write `Image A`, `Image B`, or `Image C`; mention only the mapped `@image#` tags.
- If character or wardrobe references exist, write exactly one video character-reference sentence naming the mapped `@image#` tag or tags as the sole authority for only the assigned C# appearance, face, body, wardrobe, proportions, materials, and likeness. Add a no-likeness-transfer clause only when the scene also contains unreferenced people or characters.
- If prop, object, location, or style references exist, cite their mapped `@image#` tags in `VISUAL STYLE`, `ENVIRONMENT`, or the relevant `P##` beat, not in the character-reference sentence.

## Count, Entity, And Single-Instant Locks

Use this section as an internal writing rule for any duplicate-prone storyboard: crowds, combat, pursuit, carried/dropped objects, repeated bodies, mirrored formations, vehicles, weapons, debris, light/effect origins, or any scene where the model might omit, duplicate, or split one entity into before/after copies.

- Add an optional `[COUNT LOCK]` section to `prompt_storyboard.txt` whenever exact totals matter. Keep it short and explicit: exact total, natural role/object names, one-instance-only rule, and any required screen positions.
- For count-sensitive panels, enumerate natural role names and screen positions instead of using shorthand ranges. Prefer role-and-position phrases such as `far-left guard`, `left-front guard`, `center-front guard`, `right-front guard`, and `far-right guard` over code-like ranges when omission is likely.
- A fallen, dropped, broken, opened, blocked, glowing, damaged, wet, marked, missing, or carried entity is the same role/object continuing from an earlier panel, not an extra copy. Write `the same fallen guard remains in the rear lane` or `the same cup remains dropped at screen right`, not `repeat fallen bodies` or `repeat dropped props`.
- Every storyboard panel is one frozen instant. Do not combine two time states for the same role/object in one panel line, such as upright then falling, held then dropped, intact then broken, closed then open, or visible then missing.
- Avoid temporal connectors in storyboard panel lines: `then`, `after`, `before`, `first`, `next`, `later`, `meanwhile`, `remains ... then`, or any before/after wording. Use a single readable state such as `caught in one tipping pose`, `already lying in one lane`, `held in one hand`, or `broken on the floor`.
- Count locks apply beyond characters: use them for exact numbers of vehicles, weapons, cups, doors, screens, duplicate-prone props, reflected silhouettes, trail marks, effect origins, or debris groups when those counts affect the next panel.

## Panel Writing

Each storyboard panel line must be short, drawable, dramatically framed, and locked to one frozen instant:

`P## / viewpoint-function tag / beat name: camera angle + shot scale + composition pressure + natural role silhouette pose + screen position + object/effect state + spatial relation + visible result.`

Good storyboard panel line:

`P05 / low rear evidence / skyscraper pass: camera looks downhill from behind the rider's trailing head; the rider silhouette lies feet-first in the slide, one hand in water, simple tower blocks outside, water streaks show downhill direction.`

Better shot-tag examples:

- `low root track / dark advance`
- `overhead void / rear absence`
- `compressed profile / trap line`
- `ground insert / failed grip`
- `canted close / realization`
- `top-down geometry / encirclement`
- `long-lens crush / pursuit`
- `static wide / comic reveal`

Avoid storyboard panel lines that describe:

- Camera movement such as dolly, orbit, crane, handheld, push-in, or chase camera. Use still camera angle, viewpoint, shot scale, and composition instead.
- Numeric or named lens tags such as 24mm, 35mm, telephoto, or macro in panel body lines. If the user explicitly requests lens tags, put them only in panel headers.
- Time progression or before/after states inside one panel: no `then`, `after`, `before`, `first`, `next`, `later`, `remains ... then`, or two poses/states for the same role/object.
- Duplicate-prone carryover language such as `repeat fallen bodies`, `repeat dropped props`, `previous bodies again`, or `same action repeated`; name the same role/object and one location instead.
- Audio, SFX, music, silence, foley, or ambience.
- Final render style, lighting style, palette, material finish, or cinematic grade.
- Invisible psychology that is not shown through pose, spacing, eye-line, or object state.

## Visual Style Rules

Panel interiors must be light but readable ultra-clean blocking thumbnails, not finished illustrations:

- Use open outline shapes, simple blocking silhouettes, thin medium-light graphite linework, broad negative space, mostly white paper, and only the minimum anchor details needed to read the beat.
- Graphite linework means outline strokes only. Do not use graphite toning, gray wash, tonal modeling, or shaded grayscale fill.
- Use only large readable anchor blocks: horizon line, doorway, platform edge, vehicle block, furniture block, waterline, skyline blocks, route shape, or prop block as needed.
- Reduce props to clear state icons by shape only: held, dropped, broken, blocking, open, closed, displaced, or missing. Do not draw handles, texture, labels, material finish, product detail, blade shine, tray reflection, fabric weave, fruit detail, crate slats, puddle rendering, or other prop micro-detail.
- Keep each panel interior to the essential pose, object contact, screen position, and spatial result. If a beat contains many objects, draw only the one or two objects that change state in that panel plus one geography anchor.
- Keep pose and composition readable enough for video generation.
- Avoid overly faint hairlines, messy sketch buildup, grayscale toning, gray wash, tonal modeling, bold outlines, thick contour lines, solid filled silhouettes, black ink look, dark print effect, detailed faces, hair strands, fabric folds, material rendering, dense texture, scenic micro-detail, crosshatching, heavy shading, any panel color, duplicate bodies, ghost poses, concept-art rendering, and character-design detail.

Sheet-level design may be polished:

- Header, outer frame, section bands, and panel header strips use crisp readable dark-gray typography, thin readable rules, clear hierarchy, scene-aware spacing, and restrained graphic motifs.
- Keep scene-aware motifs outside panel interiors and non-iconic when possible.
- Do not let sheet motifs enter panel interiors.

## Video Handoff Rhythm And Escalation

Keep rhythm and escalation as a short prose handoff in `prompt_video.txt` only.

- Add one compact `RHYTHM + ESCALATION:` paragraph after `EMOTIONAL GUIDANCE` and before `BEATS`.
- Write it like `EMOTIONAL GUIDANCE`: one short natural-language sentence, or two very short sentences when needed.
- Describe the overall tempo, cut feel or continuous-flow feel, build, peak, release, or unresolved ending in prose.
- Do not write panel-by-panel score notation such as `P01 hold/L1, P02-P03 burst/L3`. Mention a P## range only when it genuinely clarifies a major phase, not as a list.
- Keep it plain text, not a table, chart, legend, footer, graphic strip, or visual instruction for the storyboard image.

Allowed rhythm values:

- `tempo`: `hold`, `slow reveal`, `build`, `burst`, `impact`, `pause`, `recover`, `final hit`
- `block`: `short block`, `medium block`, `long block`
- `beat-feel`: `clean beat`, `match beat`, `smash beat`, `held beat`, `whip beat`

Allowed escalation values:

- `L1 calm`, `L2 tension`, `L3 rise`, `L4 surge`, `L5 peak`
- `curve`: `flat`, `rise`, `spike`, `drop`, `release`, `unresolved`

Use the allowed rhythm and escalation values as internal planning data only. Convert them into compact prose for the final `RHYTHM + ESCALATION:` paragraph.

## Storyboard Prompt Shape

Keep `prompt_storyboard.txt` compact, ordered, and image-model-ready:

- Start with one scene-specific `Create a 16:9 ... storyboard sheet image.` sentence so the image format is established immediately.
- Use this section order: `[SUBJECT]`, `[HEADER]`, `[BOARD STRUCTURE]`, `[VISUAL STYLE]`, optional `[REFERENCES]`, `[CONTINUITY]`, optional `[COUNT LOCK]`, `[TEXT RULES]`, `[CONSTRAINTS]`, `[BEATS]`.
- Treat section labels as prompt organization only. `prompt_storyboard.txt` must explicitly say not to render section labels.
- Put the two visible header lines in quotes. The header may visibly contain only the quoted evocative cinematic title and quoted micro-brief line.
- Make the title feel like a short film title, not a literal file slug or technical action summary. Favor tension, place, weather, object, consequence, or ironic image over terms like `flow`, `prop chain`, `fight`, or `Kali` unless the user explicitly wants them.
- Use visual decisions instead of vague praise: layout, spacing, hierarchy, line quality, negative space, camera angle, shot scale, character placement, prop state, and spatial geography.
- Keep negative rules short and risk-based. Do not print broad catch-all exclusion lists when the prompt already defines what should be drawn.
- Aim for 5000 characters or less. Use the 5500-character tolerance only when needed for reference roles, count/entity locks, continuity, panel count, or still-panel clarity.
- For panel content, first complete `prompt_video.txt`, then rewrite each video `P##` through the Image-Prompt Beat Rewrite Contract. Do not paste video wording, process notes, or source-rule names into the final storyboard prompt.
- Each rewritten storyboard beat must be a concise drawable art-direction sentence: camera angle + shot scale + frame composition + natural role/object placement + one frozen pose/state + object contact + screen direction + spatial result.
- Remove audio, SFX, foley, ambience, music, silence, final render style, lighting style, palette, material finish, cinematic grade, detailed camera movement, lens behavior, cuts, timing, pacing, and video-only choreography unless it is visible as pose or blocking. Convert camera movement into still camera angle, viewpoint, shot scale, framing, and composition without changing the visible sequence. Keep lens tags out of panel body lines; include them only in panel headers when explicitly requested. Convert multi-state timing into one frozen panel state and preserve exact entity counts when count-sensitive.

## Storyboard Template

Save only this prompt to `kd_prompts/<short_slug>/prompt_storyboard.txt`.

```text
Create a 16:9 [mood + subject] cinematic storyboard sheet image.

[SUBJECT]
A polished modern-minimal production board for [scene premise]. The sheet should communicate [one visual purpose] clearly through camera angle, shot scale, pose, object state, screen direction, and spatial geography.

[HEADER]
Design an artistic production-board header with scene-aware typography, thin readable rules, clear hierarchy, generous spacing, and restrained graphic treatment outside panel interiors only.
The header must contain exactly these two quoted lines:
"[evocative cinematic title, 2-5 words]"
"[one compact sequence goal]"

[BOARD STRUCTURE]
Use AUTO layout with [panel count] panels.
Use compact panel headers exactly in this format: `P## / shot tag / beat name`.
Draw one panel per BEATS entry, preserve P## order, and keep each panel to one clear visual action beat.

[VISUAL STYLE]
Panel interiors are silent ultra-clean blocking thumbnails: simple open-outline silhouettes, thin medium-light graphite linework, mostly white paper, broad negative space, and only the anchors needed to read pose, object contact, screen direction, and spatial result.
Open-outline silhouettes show only outer body-mass and limb contours, with no internal anatomy, face detail, clothing detail, texture, or character-design finish. Graphite linework means outline strokes only; no graphite toning, gray wash, tonal modeling, or shaded fill.
Keep all storyboard panel interiors monochrome. Use only non-color sheet-level graphic treatment outside panel interiors. If the final video has colored energy, aura, light, wardrobe, props, creatures, or environment details, describe those storyboard elements with color-neutral shape/function wording and keep all final color and palette wording only in `prompt_video.txt`.
Effects inside panels must read as abstract attached state marks, not physical props: short trails, contact bursts, halos, dust wedges, spray arcs, smoke plumes, or impact rings tied to a visible origin.

[REFERENCES]
[Omit when no references exist. If references exist, list only role controls with natural role names, e.g. `Image A: lead silhouette, wardrobe block, hair mass only.` Do not use raw entity ID tokens.]
If a character reference applies to one role, mark it exclusive to that role only. If the scene has other character silhouettes, keep those other silhouettes separate and unreferenced.

[CONTINUITY]
Keep natural role identity, character/entity count, prop state, effect origin, screen direction, fixed geography, and start-to-end spatial result consistent across panels.
Preserve important carried, dropped, broken, open, blocked, glowing, damaged, wet, marked, or missing states as the same role/object continuing across panels, not as repeated extra copies.
When both referenced and unreferenced character roles exist, keep them distinct; do not transfer a referenced face, hair block, wardrobe block, or body type to any other role.
Keep physical props and abstract effects separate in wording and placement; never let an effect mark become a held, carried, dropped, collected, or standalone object unless the story requires a real object.
Each storyboard panel is one frozen instant: use one pose/state per role/object and avoid before/after wording such as `then`, `after`, `before`, `first`, `next`, `later`, or `remains ... then`.

[COUNT LOCK]
[Omit this section when exact totals are not at risk. Use it for count-sensitive characters, bodies, vehicles, weapons, props, repeated state marks, reflected silhouettes, trail marks, effect origins, or debris groups.]
Every count-sensitive panel must preserve exactly [count + natural role/object names] as one instance each. Never omit an entity. Never duplicate an entity.
Fallen, dropped, broken, opened, blocked, glowing, damaged, wet, marked, missing, or carried entities are the same role/object continuing from earlier panels, not extra copies.
When a group count matters, enumerate screen positions clearly instead of relying only on range shorthand.

[TEXT RULES]
Visible text: only the two quoted header lines and compact panel headers. Do not render prompt section labels, role names, entity IDs, count-lock text, notes, arrows, callouts, or any other annotations inside panels.

[CONSTRAINTS]
Avoid logos, watermarks, overlays, extra panels, insets, finished illustration, dense detail, panel color, duplicate/ghost entities, before-after copies, visible role labels, visible entity IDs, and inconsistent counts.
Avoid effect marks that resemble props, icons, labels, arrows, stickers, UI, extra characters, or floating objects.

[BEATS]
Draw one storyboard panel per visual BEAT:
BEATS:
[finished visual still-panel BEAT lines, one per P##]
```

## Video Prompt Rules

Write the video prompt from the shared sequence spine and save only it to `kd_prompts/<short_slug>/prompt_video.txt`.

Apply the Video Direction Pass when writing `BEATS`:

- Use compact director language for camera grammar, shot scale, framing, camera and lens behavior, edits or continuous-camera movement, and rhythm.
- Aim for 3500 characters or less. Use the 3850-character tolerance only when needed for handoff clarity, action cause-effect, prop continuity, camera/panel alignment, or references.
- Apply the Cinematography Layer when writing `VISUAL STYLE`: one coherent lighting key and motivated source, color-emotion palette, lens and depth-of-field feel, and atmosphere, all aligned with the cinema language.
- Format every video beat as `P##:` followed by the beat description. Do not print storyboard shot tags or beat names after the panel number.
- Each beat must preserve the matching storyboard frame while adding motion, timing, final style, and final character reference detail.
- Read each storyboard panel as a separate shot sample; preserve the same C#/object identities across panels and do not merge multiple panel poses into one shot.
- `AUDIO` sets the global music, ambience, and sound-policy direction. Keep sound details in `AUDIO`, not in individual `P##` beat lines.
- Each beat should contain visible action, spatial relation, prop and effect state, and visible result. Do not rely on abstract psychology.
- Do not pad beats with stale negatives or inactive effects, such as repeating that the floor has no marks, saying a trail tapers when no trail matters, or naming vanished entities as if they are still present. Keep only negatives that prevent a likely model error and are not already covered globally.
- Keep camera notes physically coherent. For continuous boards, use one camera path and same-lens logic unless the user explicitly requests otherwise.
- Keep cause-effect legible across beats; when action is complex, make the master geography beat establish entrances, exits, foreground, midground, background, hazards, and screen direction.
- Use active endings and visible consequences when the scene calls for a payoff or unresolved continuation.

Include:

- Handoff paragraph using `@image1` exactly once for the storyboard sheet. Keep it explicit and compact; avoid vague one-line notes. State that `@image1` controls intended order, framing, staging, and screen direction only, while the written beats and mapped references override accidental sketch errors, malformed anatomy, wrong text, stray marks, extra silhouettes, and effect scribbles.
- Continuous-shot and same-lens sentences only when relevant.
- Exactly one character-reference sentence when character or wardrobe references exist, including exclusive C# mapping. Add a no-likeness-transfer clause only if the scene also contains unreferenced characters.
- `VISUAL STYLE`
- `AUDIO`
- `ENVIRONMENT`
- `EMOTIONAL GUIDANCE`
- `RHYTHM + ESCALATION`
- `BEATS`

Do not include sheet layout instructions, storyboard purity rules, or legacy standalone planning sections such as `CAMERA + LENS PLAN` or `ACTION + STATE CONTINUITY`. The only rhythm/escalation output is the short prose `RHYTHM + ESCALATION` video handoff.

## Video Template

Save only this prompt to `kd_prompts/<short_slug>/prompt_video.txt`.

```text
Use @image1 as the storyboard layout anchor for intended shot order, camera grammar, staging, screen direction, and spatial continuity only. Render the final filmed scene from this prompt and mapped references, not the storyboard sheet, sketch style, simplified anatomy, panel text, or accidental drawing artifacts; ignore malformed props, wrong letters, extra limbs, duplicate silhouettes, stray sketch marks, arrows, icons, effect scribbles, headers, borders, and sheet typography.
Read each storyboard panel as a separate shot sample of the same scene. Preserve the intended same C#/object identities across panels and do not merge multiple panel poses into one shot.
[For continuous or developing-master boards only: state that the entire video is one continuous developing master shot with no visible cuts.]
[For same-lens continuous boards only: state one virtual lens / same-lens camera movement.]
[If character or wardrobe references exist: Use @image# as the sole authority for only C# final appearance, face, body, wardrobe, proportions, materials, and likeness; storyboard silhouettes are staging references only.]
[Only if the scene also contains C2, C3, bystanders, crowds, opponents, background figures, or any unreferenced character: Do not apply the referenced likeness to those roles; give them distinct faces, hair, wardrobe silhouettes, and body proportions.]
[If no character or wardrobe references exist: use the identity details in this prompt as the character reference.]

VISUAL STYLE: [final-video medium + lighting key and motivated source + color/palette emotion + lens and depth-of-field feel + atmosphere or texture + motion and render quality, written as one coherent look aligned with the cinema language]
AUDIO: [Global sound policy. If music is not requested: No background music or score. Use only diegetic ambience, foley, impacts, texture, and silence. If music or special audio is requested, describe its role compactly.]
ENVIRONMENT: [one short sentence: location plus 2-4 fixed anchors, lighting source, or hazard only]
EMOTIONAL GUIDANCE: [one short sentence: visible body-language and pacing trajectory only]
RHYTHM + ESCALATION: [one short prose sentence, or two very short sentences, describing overall tempo/flow, build, peak, release, or unresolved ending; avoid panel-by-panel score notation]

BEATS:
P01: [same intended camera angle, framing, and shot scale as storyboard P01 + story-motivated lens or camera behavior + trigger + movement + reaction gesture + spatial relation + final physical prop identity + final effect behavior/material if present + visible result]
P02: [same intended camera angle, framing, and shot scale as storyboard P02 + story-motivated lens or camera behavior + trigger + movement + reaction gesture + spatial relation + final physical prop identity + final effect behavior/material if present + visible result]
P03: [same intended camera angle, framing, and shot scale as storyboard P03 + story-motivated lens or camera behavior + trigger + movement + reaction gesture + spatial relation + final physical prop identity + final effect behavior/material if present + visible result]
```

## Validation

Before finalizing a kodirector request, verify:

- Both files exist under `kd_prompts/<short_slug>/`.
- `prompt_video.txt` targets 3500 characters or less and never exceeds 3850 characters. Any length over 3500 is justified by handoff clarity, action cause-effect, prop continuity, camera/panel alignment, or references, and contains no filler.
- `prompt_storyboard.txt` targets 5000 characters or less and never exceeds 5500 characters. Any length over 5000 is justified by still-panel art-direction clarity, reference roles, count/entity locks, continuity, or panel count, and still reads as a clear structured brief.
- The first `prompt_video.txt` handoff paragraph is still explicit enough to use `@image1` as a layout anchor for intended order, camera, framing, pose, blocking, screen direction, composition, and spatial continuity, while rejecting accidental sketch artifacts, malformed props, wrong text, duplicate silhouettes, and effect scribbles.
- If any prompt was shortened, verify the shortened version still has coherent action flow, prop continuity, screen direction, camera/panel alignment, setup/payoff logic, and no impossible object or character-state jumps.
- Verify the stale-negative pass: panel beats should not contain obsolete exclusions, lingering effect tails, repeated absence notes, or active references to entities that are currently vanished, transformed, or represented only by residual traces.
- The storyboard title is cinematic and scene-specific, not a literal slug, technique label, or generic action description.
- The sequence uses one coherent scene-appropriate cinema language, visible in storyboard shot tags, camera angles, shot scale progression, rhythm, internal beat naming, and the prose video rhythm/escalation handoff.
- Shot tags use `viewpoint + dramatic function`, not only neutral size labels. Generic labels such as `low wide`, `side medium`, `frontal close`, `overhead wide`, or `hero wide` should be revised unless their simplicity is a deliberate formal choice.
- The camera progression reads as an intentional visual sentence with varied pressure, scale, obstruction, axis, or geometry. Adjacent panels do not repeat the same height, axis, and shot size without a story reason.
- Each panel has one clear camera idea such as occlusion, negative space, compression, foreground obstruction, scale contrast, surveillance view, subject isolation, reflection, threshold framing, top-down geometry, ground evidence, object POV, silhouette, symmetry, canted imbalance, or impact proximity.
- `prompt_video.txt` shows a coherent camera grammar and story-motivated shot sizes, camera notes, edit and rhythm language, or continuous-camera logic.
- `prompt_video.txt` `VISUAL STYLE` carries one coherent cinematography read - lighting key and motivated source, color/palette emotion, lens and depth-of-field feel, and atmosphere - aligned with the chosen cinema language, and none of it leaks into storyboard panels.
- Complex action uses an early master geography beat and preserves entrances, exits, screen direction, foreground, midground, background, hazards, and set anchors.
- Continuous-shot boards describe one physical camera path and same-lens logic unless the user explicitly requested cuts, zooms, or stylized lens changes.
- Every video beat uses visible action, spatial relation, prop and effect state, and visible result; emotion is expressed through body language, pace, framing, spacing, or eye-line.
- Props and world details create consequences across beats instead of resetting randomly.
- The ending is active when the premise needs payoff: impact, reveal, unresolved motion, pursuit, danger, collision, transformation, or changed meaning.
- `prompt_storyboard.txt` starts with a scene-specific 16:9 storyboard sheet sentence.
- `prompt_storyboard.txt` uses this structured image-prompt order: opening format sentence, `[SUBJECT]`, `[HEADER]`, `[BOARD STRUCTURE]`, `[VISUAL STYLE]`, optional `[REFERENCES]`, `[CONTINUITY]`, optional `[COUNT LOCK]`, `[TEXT RULES]`, `[CONSTRAINTS]`, and `[BEATS]`.
- The final `[BEATS]` section uses this exact setup line before `BEATS:`: `Draw one storyboard panel per visual BEAT:`
- Prompt section labels are treated as instructions only; final visible text is limited to the quoted header lines and panel headers.
- The storyboard prompt has an artistic header, panel header strips, and AUTO panel grid.
- The header visibly contains only the quoted cinematic title line and quoted micro-brief line; it does not render field labels.
- The `[VISUAL STYLE]` section explicitly says panel interiors are silent visual-reference thumbnails.
- Panel header pattern is `P## / shot tag / beat name` by default, without numeric lens tags unless the user explicitly requests lens tags in panel headers.
- Storyboard board-structure rules use `AUTO` layout unless the user requested a specific layout.
- The storyboard prompt rewrites every completed `prompt_video.txt` `P##` beat through the Image-Prompt Beat Rewrite Contract; wording must change into finished still-image panel art direction, while P## order, storyboard shot tags, storyboard beat names, visible events, camera angles, shot scales, framing, pose/blocking, screen direction, count/entity states, physical prop states, simplified effect origins, spatial results, and visible results remain aligned to the shared spine.
- The final storyboard prompt contains no process language such as copied, converted, rewritten from video, adapted from rules, or made for any named model/product.
- `prompt_video.txt` `BEATS` use `P##:` lines only and do not print storyboard shot tags or beat names after the panel number.
- Storyboard panel sequence and video `BEATS` use the same shared sequence spine: same P## count, order, internal shot tags, internal beat names, camera angles, shot scales, compositions, core action events, character positions, count/entity states, prop and effect states, and visible results. Shot tags and beat names are visible only in `prompt_storyboard.txt` panel headers.
- Each storyboard P## maps to the matching video P## and preserves camera angle, shot scale, framing, pose, blocking, screen direction, composition, prop and effect state, and spatial continuity.
- Count-sensitive scenes include a clear count/entity lock: exact totals, natural role/object names, one-instance-only language, and screen positions when omission or duplication is likely.
- Each storyboard panel is one frozen instant with no before-after wording such as `then`, `after`, `before`, `first`, `next`, `later`, or `remains ... then`; if two time states are needed, they are split into separate P## beats.
- Fallen, dropped, broken, opened, blocked, glowing, damaged, wet, marked, missing, or carried entities are written as the same role/object continuing across panels, never as repeated extra bodies, duplicate props, ghost poses, or second versions of the same entity.
- Storyboard visual-style and constraints sections specify ultra-clean sparse blocking thumbnails, simple open-outline silhouettes, restrained detail, and consistent counts/entities.
- Storyboard rules and rewritten beats omit audio, SFX, foley, ambience, music, silence, final render style, lighting style, palette, material finish, cinematic grade, detailed camera movement, lens behavior, cuts, timing, pacing, and video-only choreography unless visible as pose or blocking.
- Storyboard color isolation is complete: final-video color and palette wording does not appear in storyboard panel headers, panel body lines, continuity/count locks, reference roles, or the quoted micro-brief unless the user explicitly requested colored storyboard panels.
- Storyboard entity-token isolation is complete: raw entity ID tokens are absent from `prompt_storyboard.txt` except for `P##` panel numbers; panel beats, references, continuity, and count locks use natural role names instead.
- Character-reference exclusivity is complete: every mapped character reference applies only to its assigned C# or natural role. If unreferenced people are present, they have explicit distinct appearance cues or a no-likeness-transfer clause; if no unreferenced people are present, no extra no-likeness clause is added.
- The video prompt uses `@image1` once and treats the storyboard as layout/staging anchor, not as final style, character-design, prop-design, text, or effect-rendering authority.
- If references exist, storyboard assigns narrow roles to `Image A`, `Image B`, and `Image C` as metadata only; `prompt_video.txt` uses only mapped `@image2`, `@image3`, etc. and never writes those metadata labels.
- `prompt_video.txt` includes one short prose `RHYTHM + ESCALATION:` handoff after `EMOTIONAL GUIDANCE` and before `BEATS`, without panel-by-panel score notation.
- Final response includes only the saved file paths and a short confirmation unless the user explicitly asks for prompt text.

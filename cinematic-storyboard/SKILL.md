---
name: cinematic-storyboard
description: Generate one composite visual storyboard sheet for animated or live-action narrative scenes. Use when directing shot order, framing, camera paths, spatial continuity, blocking, key poses, cut points, and information timing. Keep character, environment, UI, story explanation, and cinematography specifications outside the storyboard image.
---

# Cinematic Storyboard

Generate a directing artifact that answers only: **how is the scene staged and shot?** Use supplied asset images as visual references, but do not turn the storyboard into an asset board, UI specification, prompt sheet, or explanatory poster.

## Separate the production layers

Treat these as separate layers:

1. **Assets:** character masters, environment images, UI screens, props, and special devices. These determine what the world looks like. Keep them as independent image references.
2. **Storyboard:** shot order, framing, camera position and path, spatial relationships, blocking, key poses, cut points, and information timing.
3. **Video prompt:** story causality, authority or governance semantics, detailed UI meaning, reference assignments, cinematography, lenses, lighting, depth of field, exposure, editing logic, and model-specific instructions.

Do not move asset-layer or prompt-layer content into the storyboard image. If the user also asks for prompts, deliver them separately after the storyboard; they are not part of this skill's visual output.

## Verify assets before storyboarding

Identify the character, environment, UI, prop, and device references required by the scene. Use them only to maintain identity and spatial consistency.

If a required visual asset does not exist, flag it as a separate asset need. Do not design the missing character, room, prop, or detailed UI inside the storyboard sheet. A screen in a panel may be represented by a simple block or supplied UI thumbnail.

## Determine panels by visual states

Choose panel count only from states that must be locked:

- composition and subject placement
- room orientation, screen direction, and axis continuity
- camera transition, path, start state, or end state
- action key pose or contact point
- information-reveal state

Do not divide the duration into equal intervals. Do not use a fixed 6-, 7-, or 9-panel template. Do not assume one panel equals one cut.

A continuous shot may need multiple panels for its start, transition, and end states. Label those panels as states of the same shot and do not imply cuts between them. Add a panel only when it resolves a directing ambiguity.

## Limit storyboard responsibility

Make the storyboard responsible only for:

- shot order and framing
- camera position, path, and transition
- subject placement and blocking
- screen direction, room orientation, spatial continuity, and axis
- action key poses
- explicit cut points
- viewer-attention flow and information timing

Do not use the storyboard for:

- character or costume design
- final environment, prop, or device art
- UI asset design or detailed UI copy
- story, legal, governance, or world-building explanation
- prompt annotations or production specifications
- lens, lighting, depth-of-field, exposure, colour-science, or ARRI ALEXA notes
- final rendering or presentation art

Story facts and technical constraints may guide staging, but they must not appear as explanatory content on the sheet.

## Generate one composite sheet

When visual output is requested, generate **one complete storyboard sheet containing all panels**. Do not output separate panel images unless the user explicitly requests them. Do not stop at a prose panel plan or sheet specification.

Use a clean production-board format:

- neutral white, off-white, or light-gray background
- readable multi-panel grid arranged by shot structure
- one short panel ID and shot/state label above each panel
- loose line art or restrained grayscale blocking sketches
- consistent character placement, room geometry, and screen direction
- only a few arrows where camera or action direction would otherwise be ambiguous
- clear gutter spacing and no decorative poster treatment

Use minimal labels such as `P01 / Wide`, `P02 / Push-in`, or `P06 / Confirm`. Do not place paragraphs, dense tables, prompt text, asset notes, audience summaries, or technical essays on the sheet.

## Handle screens and UI

Keep every screen or UI layer physically anchored to the wall, display, or surface established by the environment asset. Do not invent floating windows, detached HUDs, or holographic clutter unless explicitly requested.

Represent UI only at the level needed for composition and attention flow: simple blocks, cards, lines, highlights, or at most one or two essential labels. Use supplied UI assets for actual design and content. Never recreate a detailed UI specification inside a panel.

## Preserve normal-playback clarity

Give each shot one primary visual claim. Make it understandable through composition, grouping, scale, contrast, movement, and reveal order rather than written explanation.

Before finalizing, verify:

- the panel count follows necessary visual states rather than elapsed time
- multiple panels in one continuous shot are clearly grouped
- every cut is explicit and no accidental cut is implied
- character placement, room orientation, screen direction, and axis remain coherent
- every panel has a distinct directing purpose
- the key action pose and information reveal are legible without detailed text
- screens remain attached to their physical surfaces
- the result is one storyboard sheet, not an asset board, UI board, infographic, or prompt document

## Output

Return the single storyboard sheet as the primary deliverable. Keep any necessary external note to one compact panel list containing only panel ID, shot membership, cut/continuous status, and a short directing purpose. Do not append cinematography or video-prompt content unless the user separately requests those deliverables.

---
name: cinematic-storyboard
description: Create director-ready storyboards and companion AI-video prompts for animated narrative scenes. Use when a scene needs panels chosen by composition, spatial continuity, camera transitions, action key poses, and information reveals rather than equal time slices; also use when adding controlled cinematic language while preserving animation style.
---

# Cinematic Storyboard

Create a directing artifact, then write the requested video prompts. Establish the story facts, reference hierarchy, and screen-space geography before choosing panels.

## Determine panels by visual states

Choose panel count only from the states that must be locked:

- composition and subject placement
- spatial logic, room orientation, and screen direction
- camera transition or path
- action key pose or contact point
- information-reveal state

Do not divide the duration into equal panel intervals. Do not use a fixed panel count. Do not assume one panel equals one cut.

A continuous shot may use start, transition, and end panels. Label them as states of the same shot, not as separate cuts. Add a panel only when it resolves a directing ambiguity.

## Directing scope

Make the storyboard responsible for:

- framing and shot progression
- camera position, path, and transitions
- character blocking and key poses
- space, axis, and screen-direction continuity
- cut points
- viewer-attention flow and information-reveal order

Do not use it for character design sheets, environment/prop asset design, detailed UI copy, story explanation, production notes, or final artwork. Keep captions short and functional. Treat reference images for character, setting, and interface as the visual authorities; treat the storyboard only as the blocking authority.

## Visual storyboard sheet format

When the user asks for a visual storyboard image, output **one composite storyboard sheet containing all panels by default**, unless the user explicitly requests separate panel files.

Use a clean Koda-style production board:

- one neutral white, cream, or light-gray sheet
- panels arranged in readable rows according to shot structure
- panel ID and concise camera/state label above each panel
- minimal line-art or grayscale blocking drawings
- consistent character, room orientation, and screen direction
- small arrows only when needed to clarify camera or subject movement

Do not turn the sheet into an infographic, style bible, UI specification, production dashboard, or explanatory poster.

Do not include long paragraphs, dense tables, detailed UI copy, asset notes, color palettes, audience summaries, or technical essays inside the storyboard image.

For interface scenes, represent only the minimum visual relationship required for blocking and attention flow. Use simple cards, lines, status blocks, or one or two essential labels. Detailed UI content remains the responsibility of UI assets and the video prompt.

Multiple panels may belong to the same continuous shot. Group them visually by row or concise shot label; do not imply a cut between them unless a cut is explicitly specified.

## Screen and interface rule

Anchor every screen or UI layer to a physical wall, display, or surface named by the brief. Do not invent floating windows, holographic clutter, or detached HUDs unless explicitly requested.

For governance or interface scenes, stage causal clarity in this order: existing system state, character realization, deliberate action, resulting system state. Keep the character's authority visually distinct when that distinction is story-critical.

## Normal-playback clarity

Assume the audience watches once at normal speed. Do not rely on pausing, zooming, screenshots, or reading dense dashboards.

For each shot, define one primary visual claim. Critical interface states should be understandable through grouping, scale, contrast, motion, and composition rather than paragraphs of text.

Use no more than one dominant entity or label, one dominant status or relationship, and one secondary supporting cue per shot. Treat legal text, transaction IDs, intermediate company names, sidebars, and audit logs as background texture only.

Before approving a storyboard, verify:

- the primary relationship is understandable without reading small text
- each shot has one main information task
- the key entity or state is visually dominant
- changed and story-critical unchanged states can be distinguished
- the causal story remains understandable at normal playback speed

## Output format

For each shot, provide: shot ID and duration; whether it is a cut or continuous move; purpose; panel states; framing; screen direction/space; camera move; blocking/key pose; and only the minimal essential labels. State why a panel exists when that is not obvious.

Then provide the requested video-prompt versions. For a B prompt, include references plus storyboard authority. For a C prompt, add the cinematography layer below without changing the B story, references, or blocking.

## Cinematography layer for animated video

Keep the style explicit: mature semi-realistic seinen animation, 2D digitally painted animation world, not photorealistic, not live action. Apply cinematic language to the animated world; never ask the model to turn it into a photographed human production.

When useful, specify:

- ARRI ALEXA 35-inspired exposure and tonal response
- spherical cinema-lens perspective and focal-length intent
- practical-motivated lighting, highlight roll-off, shadow separation, and restrained contrast
- depth-of-field that preserves story-critical architecture and UI legibility
- composition, exposure priorities, and controlled camera movement

Use these as desired visual behavior, not claims of literal camera capture. Avoid clipped highlights, crushed blacks, neon cyberpunk color, handheld shake, flashy transitions, or lens effects that conflict with the brief.

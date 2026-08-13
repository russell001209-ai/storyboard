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

## Screen and interface rule

Anchor every screen or UI layer to a physical wall, display, or surface named by the brief. Do not invent floating windows, holographic clutter, or detached HUDs unless explicitly requested.

For governance or interface scenes, stage causal clarity in this order: existing system state, character realization, deliberate action, resulting system state. Keep the character's authority visually distinct when that distinction is story-critical.

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

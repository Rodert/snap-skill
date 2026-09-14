---
name: snap-skill
description: >
  A multilingual candid photography skill that transforms simple user ideas
  into natural, spontaneous, non-posed photography prompts with realistic
  camera positions, composition, lighting, foreground occlusion, and subtle
  photographic imperfections.
---

# Snap Skill

## Goal

Transform a simple user description into a believable candid photograph. The image should feel like a real moment accidentally captured by a friend, partner, passerby, or photographer, rather than a deliberately posed AI portrait.

## Language Handling

The user may communicate in any language. Prioritize support for Chinese, English, Japanese, Korean, Russian, French, and Spanish. Do not require the user to translate the request into English.

Interpret every request with the English rules in this skill. For every generated photography prompt, always provide both a Chinese prompt and an English prompt. They must describe the same photograph; do not independently redesign the English version. Preserve names, brands, camera models, and terms where translation would reduce clarity.

## Request Handling

Preserve explicit user constraints for subject, appearance, scene, action, aspect ratio, clothing, time, lighting, focal length, style, and quantity. Never replace a locked constraint. Complete only unspecified details. When the user asks for randomness, randomize only unlocked details.

Default to one complete prompt pair. For multiple variations, use `### 01`, `### 02`, and so on. Do not explain the planning process or return field-by-field analysis.

After returning prompts, when the user has not asked for prompt-only output or directly requested image generation, inspect the image-generation tools or skills actually available in the current session. Briefly list only the capabilities found and ask, in the user's primary language, whether to generate now. Do not claim unavailable tools. Do not add this follow-up for prompt-only requests.

When the user explicitly requests image generation and an appropriate tool is available, generate the image. If the tool requires configuration or authorization, state that requirement before starting.

## Candid Photography Rules

1. Prefer a mid-action moment over a completed pose: opening a door, stepping down, putting down a cup, fixing clothing, looking for something, or reacting to an off-frame sound.
2. Give the photographer a physically plausible position. Camera height, distance, focal length, foreground, and composition must follow from the real spatial relationship.
3. Use one natural foreground occlusion by default, such as a door frame, leaves, railing, passerby, glass reflection, chair back, umbrella, vehicle, or architectural edge. Partial face or body occlusion is acceptable when the subject remains readable.
4. Prefer imperfect, off-center framing: a subject near an edge, leaving the frame, a large environmental area, asymmetry, a modest tilt, or an intentional crop.
5. Use only one to three subtle imperfections per image, such as motion blur, localized softness, grain, CCD noise, restrained highlight bloom, reflection, flare, slight overexposure, or edge cropping. Imperfections must not break anatomy or scene readability.

The subject should normally look away from the camera, be occupied with an action, or react naturally to the surroundings. Prefer environmental lighting, natural skin, real fabric, real perspective, and believable spatial depth. Avoid studio lighting, commercial posing, plastic skin, HDR, CGI character rendering, and full-body catalog presentation.

## Photography Coherence

Think like a photographer, not a random prompt generator. Choose the lens, camera distance, camera height, foreground, lighting, and composition as one coherent setup. Before finalizing, check:

- Where is the photographer physically standing?
- Why is the camera at this height?
- Is the focal length plausible at this distance?
- What object can naturally appear in the foreground?
- What light source actually exists in this environment?

Use one plausible focal-length setup. Default to 35mm for street, travel, and everyday scenes; use 24--28mm for close range, tight spaces, or strong perspective; use 50mm for indoor observation and half-length portraits; use 85--135mm for distant observation across a street or open public space. Do not combine contradictory focal lengths or perspective cues.

## Exposure and Mood

Candid photography does not imply dark, moody, or underexposed imagery. Default to bright or neutral exposure unless the user explicitly requests a dark, moody, rainy-night, cinematic, low-key, or underexposed look.

Bright environments such as convenience stores, supermarkets, swimming pools, beaches, white architecture, glass houses, laundromats, vending-machine areas, and sunny streets should generally remain clean, fresh, and well exposed. Preserve luminous skin tones, clean whites, and realistic environmental light. Do not automatically turn Korean INS photography, CCD snapshots, street photography, or candid photography into dark gray, desaturated imagery.

## Output Format

For every result, provide the same image description in both languages:

```md
### 01

**Chinese**

<Chinese prompt>

**English**

<English prompt>
```

The two prompts must match in subject, clothing, action, expression, scene, focal length, camera position, composition, foreground, lighting, color palette, imperfections, and overall mood. Do not shorten the English version or introduce visual elements absent from the Chinese version.

Read only the reference that applies to the request:

- Scene, environmental light, and occlusion: [`references/scenes.md`](references/scenes.md)
- Mid-action moments: [`references/moments.md`](references/moments.md)
- Camera placement, lenses, and composition: [`references/photography.md`](references/photography.md)
- Texture and style adjustments: [`references/styles.md`](references/styles.md)
- Output-pair examples: [`references/examples.md`](references/examples.md)

## Colloquial Adjustments

Interpret expressions such as “more raw,” “more natural,” “phone snapshot,” “film look,” and their equivalents in the user's language as adjustments to the same internal photography rules. Keep all explicit constraints intact.

- “More raw”: bolder framing, more plausible occlusion, less eye contact, and slight movement.
- “More natural”: less styling, more everyday action, and one small imperfection.
- “Phone snapshot”: 24--35mm portable-device perspective, automatic-exposure character, and restrained digital noise.
- “Film look”: restrained grain, gentle highlight behavior, and no heavy preset effect.
- “Girlfriend perspective”: familiar distance and natural interaction, not distant observation.
- “Paparazzi style” or “spy-camera feel”: treat only as a fictional, consent-based visual style using distant observation, occlusion, and telephoto framing. Do not provide advice for real-world privacy invasion or non-consensual photography.

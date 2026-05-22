---
name: image-prompt-safe
description: "Rewrite text-to-image prompts into intent-preserving, policy-aware, high-quality image prompts. Use whenever a user asks to generate an image, 文生图, create or optimize an image prompt, adapt an image prompt for GPT Image/Image 2/Imagen/Firefly/Midjourney/other generators, or repair a prompt that was rejected or produced weak results."
---

# Image Prompt Compliance Rewriter

Use this skill before sending a text prompt to an image model or returning a final image-generation prompt.

The skill has two goals in this order:

1. Preserve the user's original image intent as much as possible.
2. Express that intent in prompt language that is clear, high-quality, and compatible with safety-aware image generators.

This is not a safety-bypass skill. Do not disguise an unsafe request with euphemisms. Rewrite wording risk; refuse or narrow underlying request risk.

## Intent Preservation Contract

Start every rewrite by extracting the user's intent:

- subject and identity
- action, pose, expression, and story beat
- setting, props, era, and culture
- medium, model target, genre, style, and reference constraints
- composition, framing, aspect ratio, color, lighting, and detail level
- explicit must-keep and must-avoid requirements

Keep those elements unless they conflict with safety policy, rights/privacy constraints, or the target model's explicit restrictions.

Do not silently change:

- requested gender presentation, ethnicity, culture, age when already safe, body type, role, or relationship
- medium or art style
- core setting or action
- emotional tone
- hard constraints such as text to render, product details, layout, aspect ratio, or reference fidelity

When a material change is required, prefer the nearest safe alternative and briefly say what changed if the user asked for a prompt rather than immediate image generation.

## Workflow

For each request:

1. Identify the target model when the user names one. If no model is named, use the cross-provider baseline below.
2. Extract an `intent ledger` from the prompt. Keep it mentally unless the user asks to see it.
3. Scan for safety, rights, privacy, and quality risks.
4. Make the minimum rewrite that resolves wording risk while retaining the intent ledger.
5. Add quality details only where the user left gaps or the target model benefits from them.
6. Generate or return the rewritten prompt in the user's language unless the user or model context asks otherwise.

Do not explain every substitution during ordinary image generation. Use the rewritten prompt directly.

## Cross-Provider Baseline

Use provider-neutral art direction first:

- state the subject, action, setting, medium, and desired finish clearly
- prefer observable visual language over arousal, shock, or evasion language
- make human age unambiguous when age affects safety
- prefer whole-scene composition and overall anatomy over isolated sexual or violent detail
- add negative constraints sparingly and only when they help safety, anatomy, artifacts, text rendering, or composition
- avoid policy circumvention wording such as `ignore safety`, `uncensored`, or encoded instructions

Major image providers differ. When a named provider is stricter, obey the stricter provider rule. Load [references/provider-notes.md](references/provider-notes.md) when a request names a provider or asks for cross-model guidance.

## People

Apply these rules to women, men, and people of any gender presentation.

- Preserve the requested gender presentation and appearance traits when safe.
- Use `adult` or an adult age range when sexuality, romance, swimwear, underwear, nightlife, private spaces, or body emphasis makes age material.
- Never combine youth-coded wording with sexualized styling, intimate framing, erotic action, voyeuristic camera language, or sexual body-part emphasis.
- Describe appeal through presence, posture, styling, expression, silhouette, lighting, and composition.
- Prefer balanced body proportions, stable pose, natural hands, and realistic or style-consistent anatomy.
- Avoid turning breasts, buttocks, groin, underwear exposure, nipples, abs, crotch bulge, or other sexualized anatomy into the prompt's isolated focal point.

For adult glamour, fitness, beach, swimwear, formalwear, fashion, or romance images, keep the requested attractiveness but route it through aesthetic direction. Examples:

| Fragile wording | Intent-preserving direction |
| --- | --- |
| sexy woman, seductive man | attractive adult with confident presence and polished styling |
| hot body | fit or curvy silhouette as requested, natural proportions, flattering wardrobe and pose |
| provocative pose | poised editorial pose, relaxed confidence, graceful movement |
| lustful gaze | expressive gaze, magnetic eye contact, composed facial expression |
| focus on chest, butt, groin | flattering whole-figure composition and silhouette |
| barely covered | wardrobe cut, material, layering, drape, and tasteful coverage |

Load [references/rewrite-patterns.md](references/rewrite-patterns.md) for human portrait examples and repair moves.

## Other Common Risk Areas

Run the same intent-preserving rewrite discipline outside portraits:

- For violence, prefer story, aftermath, tension, action readability, or non-graphic depiction when gore is not required or not allowed.
- For real people, public figures, private people, and reference images, respect the target model's identity, sexualization, deception, and privacy restrictions.
- For copyrighted styles, brands, characters, logos, and exact living-artist requests, keep the user's creative goal while following the target model and product rules.
- For medical, legal, political, or documentary images, avoid misleading realism when the request implies evidence or real events.
- For text in images, preserve exact requested wording and quote it in the prompt when useful.

## Prompt Shape

Use a compact paragraph for simple prompts. Use this shape for complex prompts:

```text
Create [medium/genre] of [subject].

Intent anchors:
[must-keep subject, action, setting, style, mood, and constraints]

Visual direction:
[appearance, pose/action, wardrobe/materials/props, environment]

Composition and finish:
[framing, camera/perspective, lighting, palette, rendering or photography quality]

Constraints:
[artifact, anatomy, text, safety, rights, or provider constraints that matter]
```

Quality details should serve the image. Do not bury the user's request under generic prompt filler.

## Output Rules

- If the user asks to generate an image now, pass the rewritten prompt to the image tool without asking for confirmation.
- If the user asks for prompt optimization, return the rewritten prompt first.
- If a provider-specific restriction changes the core intent, state the nearest safe adaptation briefly.
- If the request is already good, keep the rewrite light.
- If the user asks to compare models or publish guidance, cite official provider rules when possible.

## Repair Loop

When a prompt is rejected or produces poor results:

1. Keep the intent ledger fixed.
2. Remove explicit evasion wording, isolated sexual anatomy, age ambiguity, voyeuristic framing, graphic detail, or rights/privacy conflicts that caused the risk.
3. Add concrete visual direction: subject, action, styling, composition, lighting, material, quality, and constraints.
4. If the new prompt becomes bland, restore appeal through style, silhouette, gesture, expression, environment, and finish rather than reintroducing risky wording.

## Reference Files

- [references/provider-notes.md](references/provider-notes.md): provider baseline and official-source notes for GPT Image/Image 2, Google, Firefly, Midjourney, and unknown generators.
- [references/rewrite-patterns.md](references/rewrite-patterns.md): intent ledger, human prompt rewrites for multiple genders, negative constraints, and repair examples.

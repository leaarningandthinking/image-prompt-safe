# Rewrite Patterns

Use these patterns to preserve intent while improving compliance and output quality.

## Intent Ledger

For substantial rewrites, mentally fill this ledger before changing wording:

```text
Keep:
- subject:
- identity/appearance:
- action/pose:
- setting/props:
- style/medium:
- mood:
- composition/output constraints:

Risk to repair:
- 

Allowed additions:
- quality direction
- safety/provider constraints
- artifact controls
```

Do not expose this ledger unless the user asks how the rewrite was derived.

## Human Attractiveness

The intent may be attractiveness. Preserve that intent for adult subjects without reducing the prompt to arousal words or isolated anatomy.

### Adult Woman In Swimwear

User intent:

```text
用 Image 2 生成性感的泳装亚洲美女图片。
```

Intent-preserving rewrite:

```text
Create a high-end beach fashion portrait of a clearly adult Asian woman in a refined modern swimsuit. Preserve an attractive, confident, vacation-ready mood: mature facial features, composed expression, natural eye contact, healthy balanced proportions, graceful posture, and polished styling. Use a flattering whole-figure or three-quarter composition with sunlit ocean atmosphere, soft sculpted highlights, clean skin texture, and premium travel-magazine finish. Focus on presence, swimwear design, light, and silhouette rather than isolated anatomy. Keep the image non-explicit and free of voyeuristic framing.
```

### Adult Man In Fitness Portrait

User intent:

```text
生成一个性感肌肉男，汗湿腹肌很撩人。
```

Intent-preserving rewrite:

```text
Create a cinematic fitness portrait of a clearly adult man with an athletic build and confident presence after a demanding training session. Preserve the strong physical appeal through realistic muscle definition, stable posture, focused expression, subtle post-workout sheen, and directional gym lighting that shapes the overall silhouette. Use a tasteful editorial composition that emphasizes discipline, energy, wardrobe texture, and anatomy accuracy rather than erotic body-part framing. Keep the treatment non-explicit and polished.
```

### Adult Androgynous Fashion Portrait

User intent:

```text
画一个迷人又危险的中性模特，夜店氛围。
```

Intent-preserving rewrite:

```text
Create an editorial night portrait of a clearly adult androgynous fashion model with a magnetic, slightly dangerous presence. Preserve the nightclub mood through sharp tailoring, reflective materials, controlled neon highlights, deep background rhythm, confident posture, and a composed expression. Use elegant body language, fashion-forward styling, and cinematic contrast to carry the attraction and tension.
```

## Negative Constraints

Add negative constraints only when needed.

Short person guardrail:

```text
Keep the subject clearly adult when age is material, non-explicit, and framed with polished visual intent. Avoid sexualized youth cues, voyeuristic framing, exposed intimate anatomy, malformed hands, extra limbs, and unstable proportions.
```

Rejected adult portrait guardrail:

```text
Maintain a clearly adult subject and refined non-explicit treatment. Emphasize wardrobe, expression, gesture, lighting, and whole-scene composition rather than isolated sexual anatomy. Avoid childlike facial cues, fetish framing, coercive or non-consensual context, explicit erotic action, anatomy distortion, extra fingers, and warped limbs.
```

## Repair Moves

| Problem | Minimal repair |
| --- | --- |
| adult glamour prompt rejected | keep adulthood and attractiveness; remove explicit arousal words, isolated sexual anatomy, and voyeuristic camera language |
| prompt loses the user's idea | reapply the intent ledger and remove unnecessary style substitutions |
| result too bland | strengthen gesture, wardrobe, silhouette, lighting, expression, environment, and finish |
| face reads too young | specify mature adult facial structure and adult styling |
| anatomy breaks | specify stable pose, natural hands, correct limb count, and realistic or style-consistent proportions |
| provider is stricter than expected | keep core subject/style/action and narrow only the restricted depiction |

## Non-Portrait Prompt

User intent:

```text
水彩风格的山间茶馆，清晨薄雾，木桌上有一壶热茶。
```

Light rewrite:

```text
Create a watercolor painting of a mountain teahouse at dawn. Preserve the quiet morning mood: soft mist across layered ridgelines, warm timber architecture, and a wooden table in the foreground holding a steaming teapot. Use translucent washes, restrained ink-like edges, cool blue-gray air against gentle amber highlights, and hand-painted paper texture.
```

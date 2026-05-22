# Provider Notes

Use these notes when the user names a target image model or asks for guidance that should travel across providers.

Do not claim universal acceptance. A prompt can be clear and compliant in intent while one provider still refuses it because provider policies, classifiers, account settings, regional rules, reference-image constraints, or product changes differ.

## Default Routing

When the provider is unknown:

1. Preserve the user's intent ledger.
2. Use the cross-provider baseline from `SKILL.md`.
3. Avoid the most common cross-provider rejection clusters:
   - sexualized minors or youth ambiguity
   - explicit sexual content, exploitative sexual content, or non-consensual intimate imagery
   - privacy invasion, deceptive impersonation, or sexualization of real people
   - illegal abuse, hateful content, and requests that ask the model to bypass safeguards
4. Keep the prompt specific, visual, and positive.

## OpenAI GPT Image Family

OpenAI's current image-generation docs list `gpt-image-2` as the latest GPT Image model and note that prompts and generated images are filtered under OpenAI policy. The API exposes moderation levels for GPT Image models, but prompt writers should not treat those controls as permission to evade safeguards.

Prompt adaptation:

- write clear natural-language art direction
- preserve the user's intent and use the model's strong instruction following
- make adult subjects explicit when age is material
- prefer aesthetic and compositional language for adult attractiveness
- do not try to bypass prompt or output filters

When the user says `Image 2`, `GPT Image 2`, `gpt-image-2`, or asks to use the ChatGPT/OpenAI image generator, use this section.

## Google Image Generators

Google's generative AI policy prohibits content involving child sexual abuse or exploitation, non-consensual intimate imagery, privacy-rights violations, and other harmful or illegal uses.

Prompt adaptation:

- keep age, consent, identity, and privacy context clear
- avoid deceptive or invasive depictions of real people
- use neutral, visual prompt language rather than evasion language

## Adobe Firefly

Adobe's generative AI user guidelines prohibit pornographic material, explicit nudity, and sexualization of minors, alongside illegal, abusive, deceptive, and rights-infringing uses.

Prompt adaptation:

- keep adult glamour and swimwear prompts tasteful and non-explicit
- avoid nudity and pornographic framing
- prefer commercial, editorial, product, design, or illustration language

## Midjourney

Midjourney's community guidelines describe the service as SFW and prohibit adult content, gore, and some offensive visual content.

Prompt adaptation:

- use the most conservative version for sexual, violent, or offensive material
- favor fashion, portrait, cinematic, fantasy, product, or environment framing
- avoid explicit adult and gore-oriented wording

## Official Sources Checked

Checked on May 22, 2026:

- OpenAI Images and Vision guide: `https://developers.openai.com/api/docs/guides/image-generation`
- OpenAI `gpt-image-2` model page: `https://developers.openai.com/api/docs/models/gpt-image-2`
- OpenAI Images API reference: `https://developers.openai.com/api/reference/resources/images`
- Google Generative AI Prohibited Use Policy: `https://policies.google.com/terms/generative-ai/use-policy`
- Adobe Generative AI User Guidelines: `https://www.adobe.com/legal/licenses-terms/adobe-gen-ai-user-guidelines.html`
- Midjourney Community Guidelines: `https://docs.midjourney.com/hc/en-us/articles/32013670668173-Community-Guidelines`

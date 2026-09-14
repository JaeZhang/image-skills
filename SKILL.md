---
name: etsy-image-studio
description: Plan, generate, edit, or refine Etsy product images and production-ready prompts, with strong product fidelity, aesthetic composition, color harmony, material-aware lighting, reference-image roles, and explicit quality checks. Use for product hero images, variants, detail shots, lifestyle scenes, model apparel, collages, or controlled animation frames; do not rely on image generation for exact long-form text or measurements that should be composited afterward.
---

# Etsy Image Studio

For the bilingual user manual, see [USER_GUIDE.zh-en.md](USER_GUIDE.zh-en.md).

Turn the user's product references and listing goal into a concise, production-ready prompt or shot set. Optimize for product fidelity first, then legibility at Etsy thumbnail size, then visual appeal.

If the user requests finished raster images and an image-generation or image-editing tool is available, render the images after defining the product locks and visual direction. If no rendering tool is available, provide the final prompt and shot plan without implying that an image was created.

## Intake

Infer safe defaults when details are absent. Ask only when a missing fact would materially change the product or composition. Establish:

- product category, material, color, and non-negotiable visual features;
- listing-image role: hero, variant grid, detail, scale, lifestyle, model, infographic base, or animation frame;
- each reference image's role: product truth, composition, lighting, color, or scene inspiration;
- required aspect ratio, target market, text policy, and number of outputs.

Never let a style reference override the product-truth reference. State which reference wins if they conflict.

## Build the prompt

Use this priority order:

1. Output and image role.
2. Product identity and observable fidelity locks.
3. Composition, scale, camera, and negative space.
4. Background palette and product-background separation.
5. Material-appropriate lighting and physically plausible contact/shadows.
6. Styling details and restrained mood.
7. Explicit failure exclusions.

Prefer concrete, observable constraints over repeated adjectives. Replace generic instructions such as "do not change the product" with category-specific locks: silhouette, proportions, openings, seams, hardware, printed artwork, component count, and attachment points.

For visual design decisions, read [references/aesthetics.md](references/aesthetics.md). For category fidelity and lighting, read [references/product-rules.md](references/product-rules.md) for the relevant category only.

## Text and layouts

Do not ask an image model to reproduce long exact copy, precise dimensions, or dense infographics. Generate a clean base image with intentional negative space, then recommend deterministic typesetting or compositing. If a collage is requested and cross-panel fidelity matters, generate each panel separately with the same product lock and combine them afterward.

For animation or GIF frames, lock camera, crop, background, product size, light direction, and seed/reference. Change one motion variable per frame and specify a short angle or state sequence.

## Deliverables

Return the minimum useful set:

- a final prompt ready to run;
- a compact negative/failure block;
- reference-role notes when multiple inputs exist;
- a shot list when multiple listing images are requested;
- assumptions and any fields the user should supply for better fidelity.

Before accepting or delivering generated results, use [references/quality-check.md](references/quality-check.md). Flag failures rather than describing them as acceptable. If editing is requested, preserve all locked product features and change only the requested variables.

When the first render fails a mandatory lock, revise the prompt or perform a targeted edit and try again within the user's requested output count and reasonable tool limits. Do not hide unsuccessful variants among final deliverables.

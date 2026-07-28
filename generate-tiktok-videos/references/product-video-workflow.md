# Product Video Workflow

Use this reference to resolve stored products, inspect source assets, protect product fidelity, select a visual world, and design the shot sequence.

## 0. Resolve the product record

- If the user gives a `PV-####` ID, read its `product.md` and archived source-image list before asking for assets.
- If no ID exists, collect the minimum viable submission, allocate the next unused ID, copy original files into the product folder, and create the record.
- If the requested product differs in material, color, dimensions, structure, component count, or silhouette, create a new variant record. Do not rewrite historical identity.
- Keep generated campaigns in their project folders; add links and metadata to product history instead of copying all outputs into the library.

## 1. Establish the source hierarchy

Use this precedence:

1. User-confirmed product feature sheet for materials, dimensions, structure, functions, included parts, performance, certifications, and selling points.
2. Product images for visible shape, color, count, proportions, texture appearance, branding, and supported camera coverage.
3. Explicitly labeled creative assumptions for background, props, people, lighting, and mood.

When a specification conflicts with an image, stop and ask which variant is correct. Describe an unconfirmed surface as a visual appearance such as `wood-grain appearance`, not as a material such as `solid wood`.

## 2. Audit the source images

For every image, record:

- File or attachment label.
- Visible angle and crop.
- Product components and component count.
- Shape, proportions, color, finish, material cues, seams, joints, patterns, controls, packaging, and visible text or logo.
- Lighting or perspective that may distort apparent color or proportions.
- Details that are hidden, blurred, obstructed, or ambiguous.
- Background, captions, UI, props, and people that are not part of the product.

Reject no asset merely for being imperfect. State how its limitations constrain the shots.

## 3. Build the Product Identity Lock

Use four fields:

| Field | Content |
| --- | --- |
| Confirmed facts | Only specifications explicitly supplied or approved by the user. |
| Confirmed appearance | Only details directly visible in supplied images. |
| Uncertain or unseen | Rear surfaces, dimensions, mechanisms, contents, or materials that cannot be verified. |
| Forbidden changes | Color shifts, extra components, missing parts, altered logo, changed weave/pattern, redesigned silhouette, invented text. |
| Allowed variation | Background, lighting, framing, camera angle within known coverage, non-contact props, and credible people. |

Repeat a compressed identity-lock sentence inside each still-image prompt. Do not infer a functional or marketing claim from appearance.

## 4. Decide whether to pause

Ask one focused question before generation when:

- The desired shot requires an unseen product side or unconfirmed articulation.
- The user expects an exact logo or package text that is unreadable.
- Multiple supplied images appear to show different variants.
- The requested action could damage, misuse, or physically contradict the product.
- A factual benefit is central to the concept but has no supplied evidence.

Otherwise proceed and list the relevant assumption.

## 5. Choose the content type

Before creative planning, present exactly two choices and record one:

- **产品展示 (product showcase):** organize shots around appearance, structure, details, scene fit, and aspirational use.
- **产品评测 (product review):** organize shots around a review question, evidence setup, visible demonstrations, strengths, limitations, and an evidence-bounded verdict.

For product review, do not claim first-hand use, test results, comparative superiority, durability, comfort, or performance unless the user supplies evidence or the planned shot visibly demonstrates it.

## 6. Compare scene styles and lock the world

Before generating any style image, present 3–5 text-only directions with genuinely different setting and architecture; time, light, and palette; people and wardrobe; lens character and camera energy; best-use case; and product-fidelity risk.

Wait for the user to select one or more text options. Generate one comparable 9:16 hero reference image only for each selected option. Never generate an unselected option. After the user approves a final scene style, write a Visual World Lock covering architecture, season, time progression, light direction, palette, lens character, wardrobe, props, and grade. If the user explicitly requests several separate variants, create one lock and shot plan per style instead of mixing worlds. The product remains unchanged across all options.

## 7. Build a 15-second sequence

Use 5–7 independently generated clips. For 产品展示:

| ID | Role | Typical duration | Purpose |
| --- | --- | --- | --- |
| `S01_hero` | Overall product | 2–3s | Establish component count, silhouette, color, and proportions in a clean hero view. |
| `S02_scene-fit` | Scene coordination | 2–3s | Show how the product fits its intended environment without unsupported size claims. |
| `S03_material` | Material or surface | 2s | Show only user-confirmed material facts; otherwise depict visible surface appearance. |
| `S04_structure` | Structure and craft | 2s | Show confirmed or directly visible supports, joints, frames, controls, or construction. |
| `S05_detail` | Secondary detail | 2–3s | Feature a distinct component, finish, touchpoint, packaging element, or accessory. |
| `S06_human-use` | Human use and scale | 3s | Show one credible interaction without hiding, deforming, or misusing the product. |

For 产品评测, use: review question, evidence setup, visible feature demonstration, comparison or limitation, use case, and evidence-bounded verdict. Every evaluative statement must point to supplied facts or visible evidence.

Keep one purpose per shot and make durations total the planned runtime. Do not reduce the 5–7-shot count to save time; use batch generation and submission instead.

## 8. Select defensible camera coverage

- Use front, three-quarter, macro, overhead, or side views only when supported by reference coverage.
- Use slow push-in, lateral slider, gentle orbit, tilt, rack focus, or controlled handheld motion.
- Reserve fast whip pans, crash zooms, or speed ramps for a concept that benefits from them.
- Keep hands and bodies from hiding identity-defining product features.
- Avoid wide-angle distortion on geometry-sensitive products.
- Maintain the selected world. Variation should come from shot zone, scale, composition, controlled time progression, and camera movement—not unrelated locations.

### Motion hierarchy for a natural, non-AI look

Use this order of preference:

1. Keep the product rigid and motionless.
2. Add physically motivated environment motion on separate depth planes: near leaves, distant foliage, mist, reflections, shadows, fabric, steam, or a distant background figure.
3. Add one simple human action with clear contact points when it serves the shot.
4. Add one restrained camera move only when it does not destabilize product geometry.

Do not animate a tabletop, seam, weave, frame, leg, logo, texture, or rigid product surface. Avoid uniform motion where every leaf, reflection, and person moves at the same speed. A premium hero shot should normally contain a stable product, subtle foreground movement, slower background movement, and a small light or reflection change.

## 9. Generate and approve frames

Generate each frame independently at 9:16. After generation, compare:

1. Silhouette and proportions.
2. Component count and placement.
3. Color, material, finish, and pattern.
4. Logo and visible text.
5. Contact points with people and props.
6. Scene continuity with adjacent shots.
7. Compliance with the Visual World Lock.

Mark each frame `approved`, `revise`, or `blocked`. For a failed frame, name the exact mismatch and regenerate only that shot.

## 10. Plan clips for delivery

- Treat every approved frame as the first-frame source for the same shot ID.
- Ask for 2–4 second single-shot outputs unless the timeline requires otherwise. Use the shortest duration supported by the active model that covers the edit.
- Keep about 0.2–0.4 seconds of visual handles inside that duration. Do not automatically round every shot up to five seconds when the model bills by duration.
- Keep filenames and durations clear so the clips remain easy to edit later.
- Put typography, price, promotion, captions, legal copy, sound, and final color in the manual edit.
- Submit approved independent clips concurrently up to the provider or account limit. Poll them as a batch and QA completed outputs while others remain queued.
- Obtain one authorization for the exact paid batch after disclosing model, upload destination, clip count, durations, estimated total cost, and retry policy. Do not auto-submit alternate takes or retries.
- Before submission, verify that the current account and chosen official export/download route provide watermark-free output. Disclose any subscription or additional payment required. If the route is unknown or produces a 可灵/Kling watermark, stop before spending credits.

## 11. Deliver individual clips

- Treat approved individual clips as the completed default deliverable.
- Do not trim or concatenate clips into a review cut or final video.
- For every clip, verify the file exists, opens successfully, uses the intended aspect ratio, and passes first/middle/last-frame plus normal-speed playback checks.
- Watch the full official export and inspect all corners and moving overlay positions. Approve only when no visible 可灵/Kling watermark, platform logo, or platform overlay appears.
- Never use cropping, blurring, covering, inpainting, overlays, or screen recording to remove or conceal a platform watermark. If an official watermark-free export is unavailable, mark the clip `blocked`.
- Record each clip's filename, absolute path, model, duration, generation ID, cost, official export source, watermark status, and QA status in the delivery package and product project history.
- State clearly that full-video assembly was not performed.

## 12. Update product history

After delivery, append the date, campaign name, content type, selected scene style, project path, storyboard paths, and individual clip paths to the product record. Keep previous entries intact so the same ID can support multiple campaigns.

## Failure handling

- **Product drift:** strengthen the compressed identity lock, simplify the angle, reduce action, and regenerate the affected frame.
- **Invented rear or interior:** return to a supported angle or request another source image.
- **Bad logo or random text:** remove generated typography; preserve only legible source branding and add marketing text in post.
- **Human-product collision:** simplify the pose and specify correct contact points.
- **Inconsistent world:** reuse the approved environment, time of day, lighting direction, palette, and lens description.
- **Video morphing:** reduce camera motion and subject action; explicitly require rigid geometry, stable component count, and unchanged materials.
- **Product jumping or breathing:** remove push-in/orbit instructions, use locked-off framing or minimal optical parallax, and let the environment provide motion.
- **Surface or tabletop movement:** remove verbs that can be attached to the product; lock seams, texture, highlights, and geometry, then move only the camera or light source at very low amplitude.
- **Mechanical or uneven camera motion:** replace combined movements with one simple move, lower its distance, remove acceleration language, or use locked-off footage with foreground parallax.
- **Static hero frame:** keep the product fixed but add two or three motivated motions at different depths and speeds, such as near leaves, distant mist, soft reflections, a curtain edge, or a person crossing far in the background.
- **Approval check:** inspect first, middle, and last frames and watch the full clip at normal speed. Reject visible jumps, scale pulses, texture crawl, rigid-surface motion, sudden easing, or a completely frozen environment.
- **Slow generation:** separate active generation time from provider queue time; remove unselected-style previews, extra handles, alternate takes, and serial submission. Do not reduce the required storyboard or clip count, and do not reduce QA.
- **Watermark present:** reject the clip, verify account entitlement, and re-download only through an official watermark-free export route. Do not digitally remove or conceal the watermark. If no legitimate route exists, report delivery as blocked.

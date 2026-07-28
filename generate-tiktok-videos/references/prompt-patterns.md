# Prompt Patterns

Use these patterns after the Product Identity Lock and shot plan are approved. Write concrete visual instructions rather than adjective piles.

## Prompt order

For consistency, write prompts in this order:

1. Reference and product identity lock.
2. Selected Visual World Lock.
3. Shot purpose and visible action.
4. Environment zone and props.
5. Composition, framing, and lens character.
6. Lighting, palette, and material rendering.
7. Negative space and edit needs.
8. Fidelity and negative constraints.

## Model-neutral master prompt

```text
Use [reference image labels] as the sole source of truth for the product. Preserve exactly: [compressed identity lock].
Apply the selected visual world consistently: [compressed Visual World Lock].
Create a vertical 9:16 [shot role] frame showing [visible moment/action] in [environment].
Composition: [shot size, angle, subject placement, lens character, depth].
Lighting and material: [direction, quality, time of day, palette, material response].
Continuity: [shared world and adjacent-shot cues]. Leave [location] as clean negative space for edit-added text.
Do not add, remove, reshape, recolor, relabel, articulate, or duplicate any product component. No generated captions or promotional typography.
```

## Jimeng storyboard keyframe

Write the Jimeng prompt in natural Chinese. Refer to uploaded sources explicitly when the interface supports reference labels.

```text
以@图片[1] [及@图片[2]]中的产品为唯一外观依据，严格保留：[产品身份锁简写]。
统一执行已选视觉世界锁：[场景建筑、时间光线、色彩、镜头、人物服装与道具简写]。
生成 9:16 竖幅商业分镜关键帧：[画面时刻与动作]，场景为[环境]，[景别]，[机位和角度]，[镜头感与景深]。
[光线方向与质感]，[色彩方案]，真实呈现[已确认的材质和表面细节]。
与其他分镜保持[时间、场景、光向、色调]一致，在[位置]预留干净的后期字幕空间。
不改变产品造型、比例、颜色、材质、结构、配件数量、Logo和纹理，不增加不可见结构，画面中不生成字幕、价格、促销文字或水印。
```

Do not hardcode model-version names, reference-strength values, or UI controls that the current interface may not expose. Put those settings in a separate operator note only when confirmed.

## Seedance 2.0 image-to-video prompt

Upload the approved frame as the primary visual reference. Optionally add the archived product hero image for identity reinforcement and one licensed motion reference when it materially improves camera control. Focus the prompt on motion and sound rather than redesigning appearance.

```text
Use @Image 1 as the exact composition, product-identity, lighting, and first-frame reference. If supplied, use @Image 2 only to reinforce the unchanged product structure and component count.
Create one [duration]-second continuous 9:16 commercial shot.
Primary action: [one product/person/environment action with timing].
Camera: [one movement], [speed], keeping [identity-defining feature] clear and stable.
Physical behavior: [credible contact, weight, fabric, liquid, foliage, reflection, or shadow response].
Timing: hold briefly, begin [action], reach [end state], then settle for an editable end handle.
Audio: [subtle location ambience and one motivated foley cue / silent if the interface supports it]; no speech, lyrics, or dominant music unless requested.
Keep the product rigid and unchanged: identical silhouette, proportions, color, material, component count, pattern, and logo throughout. Preserve the environment, lighting direction, and composition from the first frame.
No cuts, no transition, no morphing, no extra parts, no disappearing parts, no geometry drift, no texture crawl, no random text, no watermark, no sudden camera acceleration.
```

## Naturalism-first motion pattern

Use this pattern for Kling, Seedance, or another image-to-video model when avoiding an artificial AI look is the priority:

```text
Treat the product as a rigid, motionless anchor. Lock its screen position, scale, silhouette, seams, texture, component count, and contact with the ground throughout the shot.
Primary motion source: [environment / person / camera].
Natural motion layers: [near foreground motion], [slower background motion], and [subtle reflection, shadow, mist, fabric, or light response], each physically motivated and moving at a different low amplitude.
Camera: [locked-off or one simple move only]. Use constant, restrained speed with no acceleration pulse or combined orbit-plus-zoom behavior.
Do not animate the product surface. No product jumping, breathing, scale pulsing, sliding, texture crawl, seam drift, highlight crawling, mechanical easing, synchronized foliage, or frozen background.
```

For material and structure shots, prefer:

```text
Locked camera or an almost imperceptible straight slider move. The rigid surface, seams, weave, frame, and texture remain pixel-stable; only depth parallax, focus, or physically caused light response may change.
```

For hero shots, prefer:

```text
The product remains completely still. Create life through two or three restrained environmental layers at different depths and speeds, such as a nearby leaf edge, slower distant foliage or mist, and a subtle reflection or shadow change. Add at most one small camera move.
```

Seedance 2.0 supports multimodal references and long multi-shot generation, but default to one approved storyboard frame and one editable shot per task. Use multi-shot generation only when the user explicitly prefers speed over per-shot control. Do not hardcode UI-only duration, resolution, sound, or reference settings until the current interface confirms them.

Chinese prompts are acceptable. Use English filmmaking terms only when they make the camera instruction more precise.

## Motion vocabulary

Choose one primary camera instruction:

- `slow push-in`: gradual emphasis without changing the product angle.
- `lateral slider`: clean parallax for a premium commercial feel.
- `gentle orbit`: reveal supported three-quarter geometry; avoid with only a frontal reference.
- `tilt down/up`: connect context to product.
- `rack focus`: shift attention between a prop and a confirmed detail.
- `locked-off`: stabilize human interaction or subtle environmental motion.
- `controlled handheld`: restrained lifestyle realism, not shaking.

Choose one primary subject instruction:

- light moves across a confirmed surface.
- a hand approaches and makes one anatomically correct contact.
- fabric, foliage, steam, water, or shadows move subtly around a rigid product.
- a person enters, uses, or leaves the scene without covering key features.
- the product remains still while the environment supplies motion.

## Negative prompt library

Use only relevant items:

```text
product redesign, altered silhouette, wrong proportions, color shift, material change, extra component, missing component, duplicated product, warped geometry, bent rigid parts, floating object, incorrect contact, logo mutation, random letters, promotional text, watermark, flicker, texture crawl, background jump, lighting discontinuity, camera teleport, sudden zoom, motion blur on product details
```

Do not use negative prompts to compensate for a contradictory positive prompt. Simplify the action or camera instruction first.

## Prompt QA

Before delivery, verify that each prompt:

- Names its reference source.
- Repeats the compressed identity lock in the still prompt.
- Describes only visible or user-confirmed product facts.
- Uses one shot purpose, one main action, and one camera behavior.
- Defines a credible end state and editable handle.
- Excludes generated captions and marketing typography.
- Names the single primary motion source and keeps the product static unless a confirmed function requires movement.
- Provides natural environmental motion for hero shots without synchronized or exaggerated movement.
- Uses the shortest model-supported duration that covers the planned edit.
- Includes rejection checks for product jitter, surface movement, camera easing, and frozen backgrounds.

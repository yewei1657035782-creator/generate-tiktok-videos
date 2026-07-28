---
name: generate-tiktok-videos
description: "Turn new or library-stored product references into reusable watermark-free product-video clips: register stable product IDs, choose product showcase or product review, lock product identity, present text-only scene-style options, generate reference images only for selected styles, then generate and verify individual storyboard keyframes and video clips without assembling a final video. Use for product ads, product reviews, product libraries, repeat product campaigns, ecommerce video assets, storyboard generation, 产品编号调用, 产品展示, 产品评测, 产品图生分镜, 无水印视频, or 视频片段生成."
---

# Generate Product Videos

## Core rules

Build the smallest complete package of independently usable product-video clips.

- Treat supplied product specifications as the source of truth for facts and supplied images as the source of truth for appearance.
- Never promote an image-based visual guess into a confirmed material, dimension, structure, function, or performance fact.
- Never invent dimensions, hidden surfaces, functions, accessories, claims, certifications, logos, or results.
- Preserve the product's shape, color, material, construction, component count, proportions, branding, and distinctive details across every shot.
- Ask a focused question only when missing information changes product identity, the concept, or a factual claim. Otherwise state the assumption and continue.
- Generate no marketing copy, captions, hashtags, or publishing package unless explicitly requested.
- Keep subtitles, CTA text, and graphic typography out of generated frames by default; add them during editing.
- Keep the **Product Identity Lock** stable while changing the **Visual World Lock**. Product facts and campaign style are separate controls.
- Treat naturalism and removal of the synthetic AI look as a first-class acceptance criterion. Prefer a believable locked product with motivated environmental motion over showy camera movement.
- Before creative planning, require one content type: **产品展示 (product showcase)** or **产品评测 (product review)**. Do not mix them unless the user explicitly asks for a hybrid.
- Before generating any scene-style reference image, present text-only style options and wait for the user to select one or more. Generate reference images only for the selected options.
- Treat approved individual video clips as the default endpoint. Do not trim, concatenate, or assemble them into a full video unless the user later makes a separate explicit request.
- Require every delivered clip to contain no visible 可灵/Kling watermark, platform logo, or platform overlay. This is a non-negotiable acceptance gate.
- Use only an official or licensed watermark-free export/download route. Never remove, hide, crop, blur, cover, inpaint, or overlay a platform watermark. If a legitimate watermark-free route is unavailable or unverified, mark video generation or delivery `blocked` rather than submitting or approving a watermarked clip.

## Defaults

When the user gives no production settings, use:

- Chinese deliverables with standard English filmmaking terms where useful.
- 9:16 vertical, 15 seconds planned runtime, 5–7 independently generated shots.
- 2–4 seconds per shot.
- Generate the shortest model-supported duration that safely covers the edit. Do not add paid seconds merely for generic handles; use about 0.2–0.4 seconds of usable head and tail room within that duration.
- Commercial product advertising mixed with credible lifestyle context.
- Jimeng/Image2 for storyboard keyframes and Seedance 2.0 for motion clips.
- Deliver approved clips separately with clip-level QA. Captions, sound design, transitions, final color, and full-video assembly are outside the default scope.
- Deliver only officially exported watermark-free clips; never deliver preview captures or watermarked downloads.
- For a new creative request, present 3–5 clearly different scene-style directions as text first. Generate one comparable 9:16 reference image only for each option the user selects.
- A workspace-level product library at `<workspace>/product-library`, using stable IDs such as `PV-0001`.

## Workflow

1. Resolve the product before creative work. If the user supplies a product ID, load its record and archived source images from the product library. Otherwise request the feature sheet and product images, then register the new product before generation.
2. Inspect every product image before proposing a concept. Separate user-confirmed facts from image-observed appearance.
3. Create a **Product Identity Lock** containing confirmed facts, confirmed appearance, uncertain details, forbidden changes, and allowed scene variation.
4. Present the two content types and record the user's choice before creative work:
   - **产品展示:** lead with appearance, structure, details, scene fit, and aspirational use.
   - **产品评测:** lead with evidence-backed review questions, demonstrations, strengths, limitations, and verdict; never invent test results or first-hand experience.
5. Write a compact creative brief: chosen content type, objective, audience, core promise or review question, tone, format, duration, and available assets.
6. Present 3–5 materially different scene-style directions as text only. Each option must specify architecture/setting, time and light, palette and materials, people and wardrobe, lens and camera energy, best use, and product-fidelity risks. Wait for the user to select one or more options. Generate one comparable 9:16 reference image only for each selected option; do not generate images for unselected options.
7. Ask the user to choose the final scene style after reviewing the selected reference images, unless they explicitly request separate storyboard variants for several styles. Convert each approved final style into a **Visual World Lock**: location, architecture, season, time progression, light direction, palette, lens character, wardrobe, props, and color grade.
8. Plan 5–7 single-purpose shots that follow the chosen content type. For 产品展示, use jobs such as hero, scene fit, material, structure, detail, and human use. For 产品评测, use jobs such as review question, evidence setup, visible feature demonstration, comparison or limitation, use case, and evidence-bounded verdict. Durations must add up to the planned runtime. Give each a stable filename such as `S01_hero` or `S06_human-use`.
   Before prompting video, assign each shot a motion source: `environment`, `person`, or `camera`. Keep the physical product static unless the user confirms a real product action.
9. Produce three prompt layers for every shot:
   - Model-neutral master prompt.
   - Jimeng storyboard keyframe prompt.
   - Seedance 2.0 image-to-video motion-and-audio prompt.
10. Generate each storyboard frame as a separate 9:16 image using the supplied or library-stored product image as a reference. Do not generate a grid in place of individual usable frames.
11. Compare each frame against both locks. Regenerate only failed or rejected shots.
12. After individual frames pass, arrange a numbered storyboard overview without replacing the originals.
13. Before paid video generation, verify that the current account and selected official export/download route produce watermark-free files. If this cannot be confirmed, stop before submission and report the blocker. After authorization, generate and approve the clips independently. Record model, duration, cost, generation ID, export source, local output path, watermark status, and clip-level QA for every clip.
14. Stop after the required individual clips pass. Deliver the content-type decision, selected scene style, prompt pack, asset manifest, storyboard files, individual clips, and QA result. Do not assemble a full video.
15. Append the completed campaign to the product record with date, content type, selected scene style, project path, storyboard paths, and clip paths. Do not duplicate generated media inside the product library.

Read `references/product-video-workflow.md` before analyzing assets or planning shots.
Give the user `references/product-input-checklist.md` when product facts are missing or a reusable intake form is needed.
Read `references/product-library.md` before registering, loading, or updating a product.
Read `references/creative-direction-library.md` before presenting creative directions or writing the Visual World Lock.
Read `references/prompt-patterns.md` before writing or revising generation prompts.
Use `references/delivery-template.md` for the final production package.

## Product library behavior

- Copy original source files into the registered product folder; never move or delete the user's originals.
- Assign the next unused sequential ID in `PV-0001` format. Never recycle or renumber an ID.
- Store only confirmed specifications as facts. Keep user-supplied but unverified performance claims in an evidence-status field.
- When an existing ID is requested, reuse its archived source images and parameters without asking for another upload. Ask only when a required file is missing, the requested view is unsupported, or the user wants to change the registered variant.
- Treat a material, color, construction, dimensions, component count, or silhouette change as a new product/variant record rather than silently overwriting the old identity.
- Keep `product-library/INDEX.md` as the fast visual lookup. Each active product row must include product ID, name, an embedded hero thumbnail, and a quick-call example.

## Creative direction behavior

- Present scene-style options in text before creating any style image. Style-image generation is a second, selection-gated step.
- Create real visual separation through location, architecture, time, lighting, palette, casting, styling, lensing, motion, and sound intent—not through vague adjectives.
- Generate reference images only for user-selected options. Keep selected previews comparable: same product identity, same aspect ratio, and a clear hero composition; vary the visual world.
- After selection, vary shot zones, scale, composition, and camera movement within the chosen world. Do not mix several unrelated luxury environments into one 15-second sequence.
- If the user asks for speed, they may name a stored direction or say to choose automatically; record that choice in the product project history.

## Efficiency behavior

- Keep the requested 5–7 storyboard frames and video clips. Never reduce their count as a speed optimization.
- Minimize only unnecessary generation: default to one final scene-style reference image, with no unselected styles or automatic alternate takes.
- If the user selects several scene styles, generate those reference images concurrently when the tool supports it, then require one final style before storyboards unless separate variants were explicitly requested.
- Generate independent storyboard frames concurrently after the shot plan is approved. Batch their review and regenerate only failed frames.
- Before paid video generation, show the model, clip count, duration per clip, estimated total cost, upload destination, and retry policy; obtain one authorization for that exact batch.
- Confirm the official watermark-free export/download entitlement before submitting the paid batch. If it requires a subscription or additional payment, disclose that before authorization.
- Submit approved clips concurrently up to the provider or account limit. Do not wait for one clip to finish before submitting the next when parallel submission is supported.
- Poll active jobs as a batch. Download and QA completed clips while other jobs remain queued.
- Do not generate automatic alternate takes, extra handles, unselected styles, duplicate evidence shots, or speculative retries.
- Reuse the stored product record, source images, and Product Identity Lock. For a new-style campaign, do not reuse prior generated previews, storyboards, clips, or completed videos.
- Record generation time and queue time separately so future runs can distinguish workflow delay from provider delay.

## Storyboard generation behavior

- Use image editing or reference-image generation so the product image remains the anchor.
- Generate one frame per shot and keep the same aspect ratio, product identity, visual world, and color treatment across the sequence.
- Prefer angles supported by the references. If only the front is visible, do not reveal an invented rear view.
- Do not treat AI-generated storyboard details as newly confirmed product facts.
- If the available image contains baked-in captions, UI, or a decorative background, distinguish those from the physical product before prompting.
- If image generation is unavailable, deliver complete frame prompts and clearly mark the storyboard images as pending rather than pretending they were generated.

## Video prompt behavior

- Use the approved storyboard frame as the first-frame reference for its matching clip.
- Describe motion, camera movement, timing, physical response, and end state. Do not redescribe or redesign the product.
- Keep one camera idea and one primary action per clip.
- Make de-AI naturalism the priority: the product is a rigid visual anchor; obtain life from motivated movement such as foliage, mist, reflections, fabric, steam, distant people, or foreground parallax.
- Default material and structure close-ups to `locked-off`, an extremely small slider move, or a restrained rack focus. Never ask a tabletop, rigid frame, weave pattern, seam, logo, or surface texture to animate.
- For hero shots, combine a restrained camera move with two or three low-amplitude environmental motions so the frame feels filmed rather than frozen. Every motion must have a physical cause and a different speed or depth plane.
- If camera motion risks product jitter, geometry drift, texture crawl, or mechanical easing, remove the camera move before weakening the product lock.
- Prefer restrained, physically credible movement for products. Avoid morphing, unfolding, floating, or moving parts unless confirmed by the source material.
- Design clips with economical editable handles inside the chosen duration; default to the shortest supported duration that covers the timeline.
- Generate clips independently; do not default to a single AI-generated multi-shot movie.
- Approved individual clips are the default endpoint. Do not concatenate, trim into a timeline, or create a review cut.
- Inspect at least the first, middle, and last frame plus motion playback before approval. Reject product jumping, breathing, scale pulsing, surface movement, uneven slider speed, sudden easing, frozen environment, or synchronized background motion.
- Inspect the entire exported clip, including all corners and any moving overlay positions, for a visible 可灵/Kling watermark, platform logo, or platform overlay. A `no watermark` prompt is not proof of a watermark-free platform export.
- Reject any watermarked preview, screen recording, or downloaded file. Re-download only through an official watermark-free route when the account is entitled; otherwise mark the clip `blocked`.

## Revision protocol

When the user requests changes:

1. Identify affected shot IDs.
2. Preserve approved Product Identity Lock and unaffected shots.
3. Revise only the necessary prompts and frames.
4. Update dependent edit notes if timing or transitions change.
5. Re-run identity and continuity checks on the revised shots.

## Completion gate

Do not call the package complete until:

- Each shot has an ID, duration, role, reference source, prompt layers, negative prompt, and edit transition.
- Durations match the requested total.
- Every generated frame has been checked against the Product Identity Lock.
- The product was loaded from or registered in the product library, and its project history was updated.
- The visual Markdown index contains the registered product ID, name, thumbnail, and quick-call example.
- The chosen content type, selected scene style, and Visual World Lock are explicit.
- No scene-style reference image was generated before text-option selection, and no unselected style was generated.
- No unsupported product claim or unseen construction detail appears.
- Product-review clips use only supplied or visibly demonstrated evidence; no invented test, comparison, experience, limitation, or verdict appears.
- Every video prompt is a usable single-shot instruction tied to one approved keyframe.
- Every approved clip passes first/middle/last-frame and playback checks for product jitter, surface motion, camera smoothness, and natural environmental motion.
- Every approved clip has `Watermark QA: passed` after full-playback inspection of the official exported file.
- No delivered clip contains a visible 可灵/Kling watermark, platform logo, or platform overlay, and no watermark was removed or concealed through editing.
- Generated clip duration is the shortest supported duration that satisfies the edit unless the user explicitly chooses extra handles.
- The editor can map filenames directly to the timeline.
- Every required individual clip exists, is playable, and has its absolute path and QA status recorded.
- No full-video assembly was created as part of the default workflow.

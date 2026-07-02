---
name: brand-event-pitch
description: Create or improve marketing-event brand招商 decks and招商方案 documents. Use when the user needs marketing-event idea generation, brand招商创意, a PPT/HTML deck, Feishu/Lark/Docs-style招商方案,招商手册, outline, story, review, or PPT-to-document conversion for brand sponsorship, partnership, or campaign招商, including major campaign nodes, platform IPs, brand resource packages, activity mechanics, rights design, or commercial pitch storytelling.
---

# Brand Event Pitch

Build招商 ideas, decks, and招商方案 documents for marketing events, campaign IPs, sponsorship packages, and brand partnerships. The job is not to make pretty pages; it is to make a brand believe: **this event is a timely, credible, scarce growth field, and my brand has a clear role inside it.**

This skill bundles the public `frontend-slides` visual resources under `vendor/frontend-slides/` and adapts them for招商 decks. Use `references/style-presets.md` as招商-specific guidance and `vendor/frontend-slides/` as the richer template/style implementation library.

## First Principle

Every deck must answer four buyer questions:

1. **Why now?** The user, category, social mood, or platform node makes this moment unusually valuable.
2. **Why this platform/channel?** The organizer can turn attention into content, conversion, trust, or brand assets better than other channels.
3. **Why this event/IP?** The activity has a memorable concept, repeatable participation mechanism, and enough resource certainty.
4. **Why my brand?** The brand has a natural role, not just a logo slot; the cooperation path is concrete.

If any answer is missing, pause and fix the logic before designing slides.

## Workflow

### Phase 0: Detect Task

- **New deck**: user wants a招商 PPT/HTML deck from a brief.
- **Marketing idea generation**: user wants招商营销点子、活动创意、品牌合作玩法, or campaign IP directions before writing a deck/document.
- **New proposal document**: user wants a招商方案/招商手册/Feishu/Lark/Docs-style document from a brief.
- **PPT to proposal document**: user provides an existing招商 PPT/PDF and wants it expanded into a readable, executable招商方案 document.
- **Proposal document to PPT**: user provides a招商方案 document and wants a sharper deck/storyline.
- **Sample learning**: user provides Feishu/Lark/Docs/PPT entry points; read `references/sample-learning-task.md`, crawl the allowed scope, and extract rules into `references/` or a task-specific summary.
- **Deck review**: user asks whether a招商 deck works; review story, commercial logic, page order, and visual clarity.
- **Deck rewrite**: user has an outline or draft; rebuild the story before polishing slides.

### Phase 1: Ask Only Decision-Critical Questions

Do not ask generic presentation questions first. Ask only what changes the招商 strategy:

- Event/node: What marketing event, campaign IP, commercial node, or sponsorship property is this for?
- Brand target: Which brand categories or named brands are being invited?
- Brand objective: Is the pitch selling曝光,转化,新品首发,人群渗透,信任背书,内容资产, or综合品效?
- Hard assets: What resources are real or planned: traffic, topic, H5, search, live room, creators, celebrities, store/shelf, onsite event, media PR?
- Idea scope: Are we inventing from scratch, packaging an existing idea into a sellable招商 property, or generating alternatives for comparison?
- Proof: What data, cases, category insight, or user trend can be cited?
- Visual assets: What images/logos/key visuals/product shots/event photos/reference decks can be used? If none are provided, should the agent source public images, generate campaign visuals, or use clearly marked placeholders?
- Identity/contact: What exact organizer/brand name, logo, and contact details may appear? If the user does not provide them, leave them out.
- Output: HTML deck, PPTX-style outline, page-by-page copy, Feishu/Lark/Docs-style招商方案, review comments, or export-ready PDF.

If these are unknown, proceed with a clearly marked assumption set and surface the missing items as risks.

When the user provides Feishu/Lark document references, first try to read the source through available document tools in the current environment. If direct Feishu access is unavailable, ask for an exported Markdown, DOCX, PDF, PPTX, or page images. Do not pretend to have learned private document formatting from an inaccessible link.

For sample-learning tasks, do not manually inspect only a few obvious documents unless the user asks for a quick read. Treat the entry as a corpus: discover files, classify them, extract patterns, cluster repeated decisions, and update the learning summary with abstract rules only.

### Phase 2: Build The招商 Story

Use `references/pitch-method.md` for the story patterns and page modules.

If the task is marketing idea generation, use the idea generation rules in `references/pitch-method.md` before building any page order. A usable招商 idea must include: user participation reason, brand role, platform/resource amplification path, sellable rights, execution rhythm, and risks or missing inputs.

If the category involves beauty, skincare, personal care, fragrance, apparel, fashion, styling, outfits, seasonal newness, trend reports, or large-style-category招商, also read `references/beauty-fashion-method.md`. In these categories, the idea must sell trend ownership, suitability solving, visual desire, and a proof-to-conversion loop rather than generic exposure.

Default story spine:

1. **Open with the market moment**: one sharp human/social/category tension.
2. **Prove the platform/channel opportunity**: content behavior, commerce behavior, trust path, or conversion path.
3. **Name the event idea**: a campaign concept that compresses the opportunity into a memorable phrase.
4. **Show the event system**: stages,玩法, content mechanisms, online/offline touchpoints.
5. **Map brand entry points**: category-specific roles, not generic sponsorship.
6. **Quantify resources and certainty**: traffic, slots, deliverables, timeline, rights, exclusivity.
7. **Close with cooperation path**: packages, roadmap, next steps, and a simple closing slide. Do not add contact details unless provided.

If the target output is a document, also read `references/proposal-doc-method.md` before drafting. Documents need more explicit explanation, tables, resources, execution detail, and risk notes than decks.

When the user does not specify a document format, use the default proposal outline in `references/proposal-doc-method.md` exactly: front callout with project name, project highlights, project introduction, and招商信息, followed by seven sections from项目洞察 to活动管控规范.

For the default proposal outline, the下单步骤 and活动管控规范 sections must use the fixed wording in `references/proposal-doc-method.md`; only replace recipient, cc, project, brand, price, and package placeholders when the user provides exact values.

### Phase 3: Page-Type Assembly

Build decks from page types, not from templates:

- Insight page: user tension, category behavior, social trend, commerce shift.
- Platform proof page: audience behavior, content-to-commerce loop, search/live/store/channel synergy.
- Concept page: event name, big idea, slogan, visual metaphor.
- Mechanism page: how users, creators, brands, and official resources interact.
- Brand role page: what brands do, what users see, what business result it drives.
- Resource matrix page: rights, exposure, content deliverables, live/search/H5/PR/onsite assets.
- Roadmap page: preheat, burst, long-tail; each phase has material, action, resource, KPI.
- Package page: tiered cooperation packages, scarcity, industry exclusivity, deliverables.
- Case/proof page: comparable campaign, past result, category signal.
- Closing page: cooperation invitation.
- Local business page: city/trade-area/store insight, merchant route, transaction handoff, and down-order definition.
- Interest group page: circle tension, host/leader role, "group session" mechanism, brand props/tasks, and live/clip tail.
- AI co-creation page: public problem, creator/user submission, brand challenge, judging/awards, and reusable asset library.

For proposal documents, assemble sections instead of slides:

- 高亮块：项目名称、项目亮点、项目介绍、招商信息
- 一、项目洞察
- 二、项目介绍
- 三、核心玩法
- 四、招商权益概览
- 五、招商规划
- 六、下单步骤
- 七、活动管控规范

For PPT-to-document conversion, do not copy slide text mechanically. Extract the slide logic, then expand each slide into readable paragraphs, tables, and execution notes.

For marketing idea generation, return each idea in a compact decision format:

- Idea name and one-line concept.
- User tension or node opportunity.
- Core mechanism: what users/creators/brands/platform do.
- Brand entry: suitable categories, brand role, and visible touchpoints.
- Sellable rights: sponsorship slots, content/resource package, exclusivity, deliverables.
- Conversion or asset path: search/live/store/H5/onsite/PR/report.
- Risk and missing information.

### Phase 3.5: Theme Visual Research And Image Plan

Before generating a designed deck, read `references/image-rules.md`, understand the user's招商主题, and create a theme visual research plan. 招商 decks are image-led: most strong pages should be built around theme-relevant visuals, with text as sharp claims and annotations.

The image plan must specify:

- the visual world implied by the topic: season, crowd, city, category, product scene, cultural mood, event atmosphere, colors, texture, and motion
- which pages need hero images, collages, product/category imagery, event scenery, creator/people imagery, maps, or UI/resource mockups
- where each image comes from: user-provided asset, public/sourceable image, generated image, screenshot/mockup, or intentional placeholder
- what business point each image proves or dramatizes

If the user provides no usable images, proactively source theme-relevant public images or generate theme visuals when the environment supports it. If the environment cannot access image search or image generation, state the missing capability and use clearly marked visual placeholders instead of silently producing a text-only deck.

Do not generate a final HTML deck that is all text unless the user explicitly asks for text-only output.

### Phase 4: Visual Direction

If the user wants a designed deck, choose a visual system after the招商 story is stable:

- Use 1920x1080 fixed-stage HTML slides.
- Generate 3 visual previews only after the story spine is approved or internally coherent.
- Do not let style exploration replace commercial thinking.
- For brand招商, favor high-energy but commercially legible design: strong title statements, large data, modular resource tables, campaign-world visuals, and clear brand slots.
- Avoid generic pitch-deck minimalism when the event needs IP感; avoid decorative chaos when selling resource certainty.
- For local life-service or city business projects, show real cities, stores, routes, redemption paths, merchant clusters, and transaction components; do not make it look like only a city image campaign.
- For interest/circle projects, visualize the "局": hosts, teams, gear, tasks, live-room moments, offline tables/routes, and clip-ready highlights.
- For AI/technology projects, visualize the competition or co-creation system: prompt/material input, creator output, judging, awards, exhibition, and brand-owned assets.
- For beauty/fashion projects, visualize the actual look/effect/item/texture/occasion: model looks, product grids, outfit boards, rankings, before/after, texture closeups, style maps, and creator tutorials. Do not make it a generic lifestyle deck.

Default visual workflow:

1. Read `references/style-presets.md` for招商-specific visual direction.
2. Read `vendor/frontend-slides/STYLE_PRESETS.md` and `vendor/frontend-slides/bold-template-pack/selection-index.json` for available template candidates.
3. Pick 3 suitable visual directions and generate 3 first-slide previews.
4. Ask the user to choose one or mix elements.
5. Expand the chosen style across the full deck.

When generating HTML slides, use the bundled `frontend-slides` support files:

- `vendor/frontend-slides/viewport-base.css`
- `vendor/frontend-slides/html-template.md`
- `vendor/frontend-slides/animation-patterns.md`
- `vendor/frontend-slides/STYLE_PRESETS.md`
- `vendor/frontend-slides/bold-template-pack/selection-index.json`
- selected `preview.md` / `design.md` files inside `vendor/frontend-slides/bold-template-pack/templates/`

The bundled `frontend-slides` resources are MIT licensed. Preserve the license file when copying or redistributing this skill.

### Phase 4.5: Slide Chrome And Contact Rules

Before final output, read `references/chrome-rules.md`. Template chrome is optional decoration, not content. Do not inherit default top-left labels, department names, organizer strings, runner text, confidentiality strings, footers, author names, emails, or contact blocks from examples or templates.

Only include identity or contact text when the user explicitly provides the exact wording and asks for it to appear.

### Phase 5: Quality Gate

Before delivery, check the deck against this list:

- At least 60% of non-table slides use meaningful imagery or visual mockups tied to the招商 theme.
- Images are theme-specific, not generic decoration. The deck visibly reflects the user's event/category/crowd/season/place.
- The first 3 pages include at least one strong theme image or campaign-world visual; no text-only opening sequence.
- No unauthorized top-left header/chrome text, department label, platform label, author name, email, or contact block appears anywhere.
- The final slide is a simple closing/invitation slide unless the user provided exact contact details and requested them.
- The first 3 pages make the opportunity impossible to ignore.
- The concept is not just a name; it changes the participation mechanism.
- Marketing ideas are招商-ready, not just creative slogans: each has brand roles, sellable resources, and execution constraints.
- Every major玩法 has a brand entry point and user-facing reason.
- Rights/resources are specific enough for a sales conversation.
- The roadmap shows rhythm, not just dates.
- Data supports decisions; decorative numbers are removed.
- Brand benefit is phrased in business language: reach, trust, conversion, category ownership, content assets, or new product momentum.
- Visual hierarchy supports fast executive reading.

For Feishu/Lark/Docs-style招商方案, also check:

- The opening uses the required callout with 项目名称、项目亮点、项目介绍、招商信息.
- The document can be read without a presenter explaining the slides.
- Key resources, seats, prices, timelines, deliverables, and constraints are tabled or clearly marked as `待确认`.
- It does not invent prices, contact details, logos, organizer names, or final KPI commitments.
- It is not a PPT page-by-page transcription.

## References

- `references/pitch-method.md`:招商 story formula, page modules, and review criteria.
- `references/beauty-fashion-method.md`: beauty/fashion category logic, trend IP packaging, style/beauty lab mechanisms, ranking/list formats, and commercialization checklist.
- `references/proposal-doc-method.md`:招商方案/招商手册 document structure, PPT-to-document conversion rules, and Feishu/Lark-style formatting.
- `references/sample-learning-task.md`: batch learning protocol for Feishu/Lark/Docs/PPT招商 sample corpora.
- `references/sample-learnings.md`: distilled lessons from reference招商 decks.
- `references/image-rules.md`: image-led deck rules, image planning, sourcing, and no-text-only constraints.
- `references/chrome-rules.md`: rules for page headers, footers, logos, organizer names, and contact details.
- `references/style-presets.md`:招商-specific visual direction layer used to choose and adapt templates.
- `vendor/frontend-slides/`: bundled public visual resources and bold template pack, from `frontend-slides` under MIT License.

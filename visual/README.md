# Visual direction

Working document for the visual style of the Sachkov Inside landing. Filled
iteratively from the product character (see `product/README.md`) and the
reference collection (see `references/`).

Status: **direction chosen and confirmed de-facto through iterative prototype
work (2026-08-17/18): A2 «мягкая спецификация + глитч»**, prototype
`visual/prototypes/a2-spec-soft.html` is the reference implementation for the
Astro port.

Earlier prototypes for comparison: `index.html` (hub), `a-spec.html`,
`b-console.html`, `c-workshop.html`. Self-contained static HTML, not
production code.

## Signals from the product

Character keywords: engineering, alive, authorial, open on the inside,
professional without corporate coldness, technological without hype, dense in
value, honest.

Existing asset: pixel-art Telegram avatars (working launch direction; does not
constrain the landing's own style).

## Direction A2: soft spec + glitch

### Mood

Warm engineering. Soft, rounded, tactile (clay 3D objects), but technical in
register (mono labels, spec numbers, terminal). Not: strict/sharp corporate,
not dark hacker neon, not AI-slop stock gradients.

### Palette

- Paper background `#F6F4EF` with a live dot-grid canvas (cursor-reactive on
  desktop, periodic sweep on mobile).
- Ink `#16130E` (warm near-black) for text and dark panels (bento, final CTA).
- Accent orange `#F26B1D` (CTA, checks, highlights, clay-object glows).
- Secondary teal `#2A9D8F` for AI topics (chips, tile accents).
- Hairline borders `rgba(22,19,14,.09)`, soft shadows, radius 16–30px.

### Typography

- Headings/UI: bold grotesque (system stack in prototype), tight tracking
  (-0.02em), big fluid H2 `clamp(28px, 4vw, 44px)`.
- Mono (JetBrains Mono style stack) for labels, numbers (01–05), chips,
  nav, terminal: uppercase, letter-spacing 0.06–0.2em, 10.5–12px.
- Body 15–16px, line-height 1.55–1.6, muted ink.
- No em dashes (—) anywhere in visible copy — only en dash (–) or rephrase.

### Graphics & illustration

- Clay 3D objects on transparent background (generated, style-matched):
  hero computer with glowing "S" screen; bento tiles: server (production),
  robot (AI-first), modules (architecture), staircase (career), workbench
  (practice), speech bubbles (community); robot reused in the final CTA.
  Prompt template fixed in `copy/README.md`.
- Cutout author photo on a warm gradient card.
- Terminal window as a live artifact (CI/CD pipeline run) in the process
  section.
- No stock imagery, no code screenshots as decoration.

### Composition & grid

- Mobile-first (~393px primary), fluid sizing with clamp over breakpoint
  jumps; intermediate widths 700–1200px are always checked.
- Section rhythm: light paper sections alternate with one dark bento panel
  («Что внутри») and a dark final CTA panel.
- Floating nav pill (rounded, blur), safe-area aware (`viewport-fit=cover`,
  `env(safe-area-inset-*)`). Desktop ≥1024px: 5 numbered items + orange CTA;
  <1024px: brand + burger → fullscreen overlay menu; ≤480px: pill CTA hidden
  (CTA exists in every section).
- Every section ends with a quiet mono exit-CTA «Получить доступ →»
  (`.sec-cta`) to the Tribute payment page.

### Motion

- Scroll reveal (fade + 12px rise, staggered per container, once) via
  IntersectionObserver.
- Hero: glitch on «Fullstack» (7s cycle, RGB-split flashes) + gentle
  float/jitter on the clay computer.
- Tiles: float animation + orange glow + hover lift.
- Terminal: lines appear one by one when in view (once), blinking cursor.
- FAQ accordion: grid-rows 0fr→1fr, icon rotates plus → orange ×.
- `prefers-reduced-motion` disables all animation globally.
- QA hooks: `?static` (terminal lines + all reveals visible), `?faq=open`,
  `?nav=open`, `?glitch=freeze`.

## Page structure (confirmed)

Hero → Что внутри (dark bento, 6 clay tiles) → От проектирования до релиза
(terminal + 4 perks + stack chips) → Это не вайб-кодинг (5 skill cards,
Lucide icons) → Полезно на любом уровне (4 stages on a left accent rail,
«Темы этапа» panels) → Кто ведёт канал (author card) → Вопросы и ответы
(accordion, 6 items) → Заходи в Sachkov Inside (dark final CTA) → footer.
Conversion: all «Получить доступ» →
`https://t.me/tribute/app?startapp=s13EA_pc_INSIDE` (new tab); price is not shown on the landing.

## Open questions

- How should the landing style relate to the pixel-art avatars: continue,
  coexist, or replace? (Currently coexists — not used on the landing.)
- Which bento artifacts should become real screenshots at launch (if any).

## Decision log

| Date | Decision | Basis |
|---|---|---|
| 2026-08-17 | Direction A2 chosen; hero locked (H1, glitch, clay computer right) | owner review of 3 prototypes |
| 2026-08-17 | Clay 3D objects for all 6 bento tiles; micro-labels removed | owner liked clay direction |
| 2026-08-17 | Git-graph replaced by CI/CD terminal | owner: branch decor read as noise |
| 2026-08-18 | Author block: cutout photo, Russian stats, «Software Engineer» | owner edits |
| 2026-08-18 | Audience filter content finalized; FAQ as accordion (chat postponed) | owner choice |
| 2026-08-18 | Nav: 5 items + pill CTA; burger overlay <1024px; safe-area support | header overflow on tablet |
| 2026-08-18 | Conversion settled: all CTA → Tribute page, price off-site | owner provided link |
| 2026-08-18 | Final CTA panel (robot, «Заходи в Sachkov Inside») + real footer + meta/OG/favicon | closing the design phase |
| 2026-08-18 | Trust line removed from final CTA; Tribute link → /s/13EA; stack chips made solid/legible on light bg | owner polish pass |
| 2026-08-20 | Hero headline changed to «Fullstack-мастерская» | owner Agentation feedback |
| 2026-08-25 | «Это не вайб-кодинг» section after Pipeline; Fit replaced by «Полезно на любом уровне» stage rail (owner's course reference); pain thread woven through hero/craft/pipeline/FAQ/final CTA copy | owner requests |
| 2026-08-25 | Author block moved to just before FAQ; nav renumbered 03 Уровни / 04 Автор | owner request |

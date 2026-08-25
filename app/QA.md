# Astro port QA evidence

Date: 2026-08-18

Reference: `visual/prototypes/a2-spec-soft.html`

Review base: `bdd0177905df723ca4e4e2fb9288a4d8dc95701b`

## Build gate

- Red: `npm --prefix app run build` failed before the port because `app/package.json` did not exist.
- Green: `npm run build` from `app/` completed with Astro Check reporting 0 errors, 0 warnings, and 0 hints, then generated one static page.

## Responsive parity

The prototype and Astro output were compared with full-page browser screenshots. The final Astro output was checked at 320, 393, 768, 1024, and 1440 CSS pixels. Additional overflow checks covered 700, 900, and 1200 pixels.

- Document width matched viewport width at every checked size.
- No horizontal overflow or overlapping content was observed.
- The mobile navigation was present below 1024 pixels; the desktop navigation was present from 1024 pixels.
- The hero heading kept its confirmed two-line composition.
- All nine WebP images loaded with non-zero natural dimensions.

## Interaction and accessibility checks

- All ten conversion links resolve in the generated page to `https://t.me/tribute/app?startapp=s13EA_pc_INSIDE`, open a new tab, and include `rel="noopener"`.
- The mobile menu opens from the burger button, closes with Escape, restores focus, and locks body scrolling while open.
- FAQ items toggle independently and keep `aria-expanded` and `aria-controls` in sync.
- Reduced-motion mode disables the glitch, reveal, terminal, floating-object, navigation, CTA, and social-link motion.
- The deterministic `?static`, `?faq=open`, `?nav=open`, and `?glitch=freeze` QA states work.
- The accessibility tree exposes `Software Engineer` once in the main heading.
- A browser context with JavaScript disabled exposed the six-link semantic fallback navigation, kept the inert burger hidden, and had no horizontal overflow at 393 pixels.
- Browser console checks reported no errors or warnings.
- Visible page text contains no em dash characters.

## Boundaries

- The Tribute target and link behavior were verified; no external checkout or payment was completed.
- Production Core Web Vitals require a deployed URL and real traffic, so they are not verified here.

## Timeweb production build

- `npm run verify` completes with Astro Check reporting 0 errors, 0 warnings, and 0 hints, then validates the production canonical, Open Graph image, robots, sitemap, and health endpoint in the generated static output.
- Browser QA against the production build confirmed the production canonical and Open Graph URL, valid WebSite JSON-LD, nine conversion links, all nine loaded images, no horizontal overflow, no console errors, and the same 393-pixel full-page composition.
- A no-JavaScript browser check confirmed the six-link fallback navigation and hidden inert burger.

The actual Timeweb deployment, domain rebinding, external Tribute checkout, and field Core Web Vitals remain post-push operational checks.

## Craft + Levels sections (2026-08-25)

Scope: new «Это не вайб-кодинг» section (`#craft`, after Pipeline) and the
«Полезно на любом уровне» railway timeline (`#levels`, replacing Fit). Nav item
«04 Кому подходит» renamed to «04 Уровни» in pill, overlay and no-JS nav.

- Green: `npm run verify` completed with Astro Check 0/0/0 and production metadata verified.
- Screenshots at 1440x1000, 768x1024, 393x852, and 320x568 in the deterministic `?static` state: both sections compose correctly; the desktop rail runs horizontally with the filled senior node, below 900px it collapses to a vertical rail.
- No horizontal overflow at 320, 393, 768, or 1440 CSS pixels.
- Browser console reported no errors or warnings.
- Ten conversion links resolve to the Tribute URL, including the new per-section CTA links in `#craft` and `#levels`.
- Visible page text still contains no em dash characters.
- New hover transitions (`.craft-card`, `.level`) are disabled under reduced motion; section content is plain semantic HTML visible without JS.

Update 2026-08-25 (second pass): craft card glyphs replaced with inline Lucide icons on accent discs; the levels rail reworked to a vertical timeline (central rail, alternating cards ≥900px; left rail below; ring nodes with paper halo, filled senior node). Copy revised through the owner's natural-text rules. Re-verified: `npm run verify` green, no overflow at 320/393/768/1440, dev-server screenshots checked at 393/768/1440.

Update 2026-08-25 (third pass): levels reworked from the owner's SachkovLearn course reference — stages top-down along a left accent rail at every viewport, mono pill badges, outcome lines, 3 icon features per stage, «Темы этапа» panel (right column ≥900px). Reference counters (modules/lessons/projects) intentionally dropped: numbers are never invented. Verified before interruption: `npm run verify` green (Astro Check 0/0/0), production preview console clean, no overflow at 320/393/768/1440, screenshots checked at 393/768/1440.

Update 2026-08-25 (pain-thread copy pass): owner's pain narrative woven through existing copy — hero sub, craft lead, pipeline perk «Живой продукт…», new FAQ 05 «У меня уже есть курсы и гайды…» (cancellation item renumbered to 06), final CTA sub («Небольшая цена подписки вместо дорогого курса»). Copy-only change, no layout or style edits.

Update 2026-08-25 (author reorder): «Кто ведёт канал» moved between Levels and FAQ; nav renumbered 03 Уровни / 04 Автор in pill, overlay and no-JS nav. Section order and anchor ids unchanged otherwise.

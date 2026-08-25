# Copy & block map

Working document for the landing's structure and copy: the ordered list of
blocks, each block's job, its copy (Russian, draft) and its illustration/artifact.
Filled iteratively — per block the owner sends a reference or picks from
proposed variants. Source of truth for the product: `../product/README.md`.
Visual language: direction A2 (see `../visual/README.md`,
prototype `../visual/prototypes/a2-spec-soft.html`).

Status: **draft block map, under discussion**. Nothing here is final copy.

Rules: claims, prices, testimonials are never invented — unknowns are marked
`TBD`. The conversion event is settled (2026-08-18): every «Получить доступ»
leads to the Tribute app `https://t.me/tribute/app?startapp=s13EA_pc_INSIDE`
(target=_blank); the price is NOT shown on the landing itself.

## Block map (proposal v1)

| # | Block | Job | Illustration / artifact | Status |
|---|-------|-----|------------------------|--------|
| 01 | Hero | Positioning in one screen: inside real development, to a shipped result. CTA pair. | 3D clay computer with glowing "S" screen (done, `visual/prototypes/assets/hero-computer.webp`) | prototype |
| 02 | ~~Spec strip~~ | Removed by owner (2026-08-17): carried no useful info | – | removed |
| 03 | Что внутри | Explain what the membership consists of: production materials, AI-first, architecture, career, practice, community. | dark bento panel + 6 artifact tiles (first iteration in prototype; awaiting owner references for rework) | iterating |
| 04 | От проектирования до релиза | Full production cycle (not one build-series): design+architecture and AI-first first, code secondary; 4 benefits; stack chips. | light section with terminal window running the CI/CD pipeline line by line (prototype) | iterating |
| 05 | Кто ведёт канал | Trust: real engineer behind the channel, public track record. | white card: cutout photo (`assets/author.webp`) on warm gradient + facts, stats, CTA «Написать мне», social icons | prototype |
| 05b | Это не вайб-кодинг | Anti-hype positioning: AI writes the code, but production rests on engineering skills: clean code, review, microservice design, business tasks, priorities. | light section, H2 with «вайб-кодинг» struck through in accent, 5 skill cards with inline Lucide icons (braces / search-code / network / target / arrow-up-narrow-wide) | prototype |
| 06 | Три направления (Архитектура / AI-агенты / Production) | What the practice covers; AI as practice, not decoration. | numbered 01/02/03 columns (prototype) or per-topic mini-artifacts | to discuss |
| 07 | Комьюнити | Separate chat, Kirill's participation, breakdowns and streams; not mentorship. | TBD — proposals: chat message cards / stream schedule strip | to discuss |
| 08 | Полезно на любом уровне | Per-grade value: начинающий / junior / middle / senior each take what their stage needs. Replaces «Кому подходит / кому нет» (owner decision 2026-08-25). | stages top-down along a left accent rail at every viewport: ring nodes on a paper halo, senior node filled; each stage = mono pill LVL 01–04, title, «кто ты сейчас» line, accent outcome line, 3 features with inline Lucide icons + «Темы этапа» panel (right column ≥900px, below on mobile) | prototype |
| 09 | FAQ | Objection handling: language fit, not-a-course, time, answers, cancellation. | soft accordion cards (mono index, plus/minus), `?faq=open` debug param | prototype |
| 10 | Формат и доступ | Closing CTA; price and checkout live on the Tribute page, not on the landing. | dark panel «Заходи в Sachkov Inside» + clay robot + big CTA | prototype |
| 11 | Footer | Brand, social links (TG/YT/GitHub), copyright. | mono row, stacked on mobile, safe-area bottom inset | prototype |

## Open questions

- Price and terms live on the Tribute page, not on the landing.
- Which artifacts in block 03 are real at launch (screenshots of actual
  ADRs/posts vs. stylized mock artifacts).

## Notes per block

_Discussion decisions land here as we go, newest first._

### Author block moved before FAQ (2026-08-25)

Owner request: «Кто ведёт канал» now sits between Levels and FAQ (was between
Craft and Levels). Page order: Hero → Что внутри → Pipeline → Craft → Levels
→ Author → FAQ → Final CTA. Nav renumbered accordingly in the pill, overlay
and no-JS nav: 03 Уровни / 04 Автор / 05 FAQ.

### Pain thread across the landing (2026-08-25)

Owner request: the landing must say which pain the workshop solves, woven
through the whole page. Pains from the owner's voice notes: tech moves too
fast and AI is already applied everywhere; full courses are expensive; design
and production-development skills are what's missing; plain guides (a CRUD, a
single line of code) lose relevance; the membership is for those who want to
keep growing: useful materials for a small subscription price. Threaded into
existing copy, no new section: hero sub («Технологии меняются каждый месяц.
Разбираем те, что востребованы сегодня, и практики, которые актуальны всегда:
…» — H1 untouched; owner picked this variant from four: the first draft
«гайды устаревают ещё быстрее… то, что остаётся» read as evergreen-fundamentals
only and hid the current-tech side),
craft lead («обычные гайды про синтаксис теряют смысл»), pipeline perk
«Живой продукт, не записанный курс» («Полноценный курс стоит дорого и
устаревает к моменту выхода»), new FAQ 05 «У меня уже есть курсы и гайды.
Чем это отличается?» (old cancellation item renumbered to 06), final CTA sub
(«Небольшая цена подписки вместо дорогого курса»). Copy follows the owner's
natural-text rules; no em dashes. The price itself stays off-site on the
Tribute page; only the relative framing «небольшая цена» is used. Pending
owner pass.

### Levels rework from the owner's course reference (2026-08-25, third pass)

Owner sent his SachkovLearn .NET-course landing as a reference (dark stage
sections) and asked to adapt it to Inside, naming concrete technologies
(auth, microservices, brokers). Adapted to light A2: stages run top-down
along a left accent rail at every viewport; each stage = mono pill badge
(LVL 01 · Старт … LVL 04 · Инженер), title, «кто ты сейчас» line, accent
outcome line with «→», 3 features with inline Lucide icons, and a «Темы
этапа» panel listing concrete topics (микросервисы, PostgreSQL и Redis,
Kafka, авторизация и аутентификация, system design). The reference's counters
(«28 модулей · 93 урока · 5 проектов») were dropped: numbers are never
invented. Replaces the alternating zigzag timeline from the second pass.
Copy passed through natural-text; pending owner pass.

### 05b «Это не вайб-кодинг» + 08 «Полезно на любом уровне» (2026-08-25)

Owner request: a section against вайб-кодинг (clean code, review, microservice
design, business tasks, priorities) and a railway/timeline of per-grade value
(начинающий / junior / middle / senior). Owner decisions: the timeline REPLACES
«Кому это подходит» (Fit removed; the honest-filter role partially stays with
FAQ); «Это не вайб-кодинг» sits after Pipeline, before Author. Craft: H2 with
«вайб-кодинг» struck through by an accent stroke, lead, 5 light cards with
inline Lucide icons on accent-tinted discs (braces / search-code / network /
target / arrow-up-narrow-wide); owner rejected the first mono-glyph variant
({} ± ◈ ◎ ↑) and pointed to developer-icons as a style reference — that set is
tech logos only and does not cover these five concepts, so Lucide (ISC) paths
are inlined instead. 6-col grid (3+2) on desktop, 2 cols ≥700px, 1 col mobile.
Levels: H2 «Полезно на любом уровне», rail with gradient faint→accent and 4
nodes (senior node filled), cards LVL 01–04 with a «кто ты сейчас» line and 3
takeaways. Owner pass 2026-08-25 (second): horizontal 4-column rail read too
narrow when the window is slightly narrowed — reworked to a vertical timeline:
central rail with cards alternating left/right ≥900px, left rail below; nodes
are white rings with a 3px accent border on a paper halo that cuts the line
(senior node filled with an accent outer ring). Copy passed through the
natural-text rules (owner's personal skill): concrete lead («что строить, как
проверять, когда выпускать»), «naming» → «понятные имена», microservice card
names data/protocols/failure behavior explicitly, no em dashes. Owner pass on
LVL 01: «Первые навыки проектирования» → «Первые навыки production-разработки»
(он не учит писать код с нуля); «Практика на настоящих задачах…» → «Все примеры
из живых production-проектов» (на платформе нет заданий для выполнения, но все
примеры показываются на практике). Nav item «04 Кому подходит»
renamed to «04 Уровни» (#levels) in pill, overlay and no-JS nav. Section ids:
#craft, #levels. Copy drafted by agent from the owner's voice notes, pending
owner pass. Note: owner uses the spelling «вайб-кодинг».

### Final CTA polish + Tribute link (2026-08-18)

Owner pass: trust line «TELEGRAM-FIRST · WEEKLY · CANCEL ANYTIME» removed
from the final CTA panel (sub already says the same in Russian). Tribute link
updated everywhere to `https://t.me/tribute/app?startapp=s13EA_pc_INSIDE` (10 CTAs). Stack chips
legibility fixed on the light background: solid white fill, darker border
(rgba ink 0.18), ink text at weight 500 (was 60%-white fill + hairline +
ink-soft text); teal AI chips keep the teal accent. «Платежи» chip earlier
replaced with «Production кейсы» (owner: real production tasks over payment
integrations); perk text «от базы данных до платежей и AI» still mentions
платежи — pending owner decision.

### 09 FAQ — accordion (2026-08-18)

Owner chose a clean accordion over the chat concept for now (chat style may
return later). 5 Q&A drafted by agent, pending owner pass: single language
fit (examples mostly TS, transferable), not-a-course (living channel, pick
your topics), time commitment (own pace, chat for questions), direct answers
(1:1, breakdowns, streams), cancellation (any time, no strings). Section
«Вопросы и ответы» between fit and footer, id="faq", added to nav as
«05 FAQ». Native `<button>` + aria-expanded, grid-rows 0fr→1fr animation,
all answers visible without JS, `?faq=open` debug param. `.sec-cta` at the
end like other sections.

### Header nav + per-section CTA (2026-08-18)

Nav pill now lists all sections: 01 Что внутри / 02 Процесс / 03 Автор / 04
Кому подходит / 05 FAQ (ids added: #pipeline, #author, #fit, #faq;
scroll-margin-top 80px everywhere) + compact orange «Получить доступ» button
in the pill → #access («Доступ» menu item removed, button took its role).
Desktop ≥1024px: single row, nowrap, numbers hidden ≤1200px. <1024px:
hamburger opens a fullscreen overlay menu (5 large items + CTA, Escape /
item click / × to close, body scroll locked, `?nav=open` debug param).
Safe-area: `viewport-fit=cover`, pill top offset and overlay paddings use
`env(safe-area-inset-*)` for iPhone notch/Dynamic Island. Every section
(bento, pipeline, author, fit, faq) ends with a quiet `.sec-cta` mono link
«Получить доступ →» → #access (dark variant in bento). ≤480px: nav CTA
hidden (it's in every section anyway), pill = brand + burger only.

QA note (2026-08-18): the `--force-device-scale-factor=1.272` trick does NOT
shrink the CSS viewport in headless Chrome (layout stays at the clamped
500px width; DSF only scales the screenshot). For true 393px QA use
Playwright: `npx --no-install playwright screenshot --viewport-size=393,H
"file://...a2-spec-soft.html?static" out.png`. Earlier "393px" screenshots
were actually 500 CSS px wide. Owner's intent: the button will
lead to purchase later; keep it present in every block. The «кому подходит»
section itself is pending a visual rework (owner researching; candidates:
участника path timeline, vacancy-style spec sheet, signal chip cloud).

### 08 «Кому это подходит» — audience filter (2026-08-18)

Owner dictated the items (sense preserved, wording polished). «Подходит, если
ты:» — 6 items: knows ≥1 language, wants real projects; working developer
growing to the next level; wants AI-first development: agents, approaches and
practices that are increasingly required in real work («которые всё чаще
требуются на реальной работе», owner rejected «держат тебя востребованным»); wants the community and direct contact; wants an
ever-evolving space, not a stale recorded course; not ready to pay 100k+ for
a course, subscription costs tens of times less (implies subscription
pricing). «Не подходит, если ты:» — 3 items: zero programming; needs a strict
sequential program («это не курс»); expects a job guarantee. Two soft cards,
left wider (1.15fr/0.85fr from 900px), orange checks / muted grey crosses,
no red. Between author section and footer.

### 05 «Кто ведёт канал» — author block (2026-08-17)

Owner provided credentials from his SachkovLearn landing and a cutout photo
(processed to `assets/author.webp`/`author.png`, alpha eroded 1px, 839x1200).
Section between pipeline and footer: H2 «Кто ведёт канал», name «Кирилл
Сачков», accent facts line «Software Engineer · 5 лет опыта · 3+ года
менторства» (owner: not «.NET разработчик», channel is not .NET-only),
paragraph on SachkovLearn/YouTube/250+ учеников (owner: «Веду YouTube-канал
по разработке», no «за 3 года»), paragraph tying
Sachkov Inside to his current real-time work, spec stats in Russian
(ОПЫТ 5+ ЛЕТ / МЕНТОРСТВО 3+ ГОДА / УЧЕНИКИ 250+), CTA «Написать мне» → t.me/sachkov_blog,
social icons (Telegram, YouTube @SachkovDev, GitHub KirillSachkov). White card
on the light page, photo on warm gradient, single column below 960px
(breakpoint raised from 769px after owner QA: at 736–785px the two-column
layout blew up the photo block; stacked photo block now has fixed fluid
height clamp(300px, 50vw, 420px), `picture { display: contents }` so the
img is the flex child and height: 100% works).

### 04b Pipeline rework — terminal instead of git-graph (2026-08-17)

Owner disliked the git-graph (merge branch read as noise). Replaced with a
terminal window `sachkov-inside · pipeline`: `$ sachkov pipeline --run`, five
stages appear line by line with ✓ and timings, final `✓ release deployed →
production` with blinking cursor. IntersectionObserver plays the stagger once;
`?static` debug param forces final state for screenshots. Copy edits by owner:
lead «…покрываем весь путь разработки production-продуктов. Наберись опыта,
который важен в коммерческой разработке.»; perk «навыки, которые делают тебя
востребованным на рынке» («двигают карьеру» rejected as AI-slop); community
tile extended (комьюнити, обмен опытом, обратная связь); stack chips:
«TS / Go / C# / Java» (TS first, highlighted orange — backend language is
secondary) + Тестирование, Авторизация и аутентификация, Релиз в продакшен,
AI-разработка (teal, like AI-интеграция).

### 04 Build-блок → «От проектирования до релиза» (2026-08-17)

Owner steered away from «building one product» (there will be standalone
lessons too) toward full production-cycle coverage, with code deliberately
secondary: проектирование и архитектура и AI-first на первом месте.
Implemented as light section `.pipeline` after the bento: H2 «От
проектирования до релиза», vertical git-graph pipeline (проектирование и
архитектура → AI-first разработка → ревью и тесты → CI/CD и деплой → релиз
и мониторинг), 4 benefits (живой продукт не курс / прямой контакт / полный
фуллстек / практика для роста), stack chips (TypeScript, Backend, Frontend,
PostgreSQL, Redis, Kafka, CI/CD, Платежи, AI-интеграция). Old duplicating
«Что попадает внутрь» 01/02/03 section removed; #access anchor moved to the
footer strip. Future block noted by owner: «об авторе» (5-летний опыт),
between Сообщество and the audience filter.

Owner decision: the strip carried no useful information («Private / Telegram /
Weekly / Real work only») and crowded the hero. Removed from the prototype.
If real numbers appear before launch (counts of materials, cadence facts),
a factual strip may return near the access block.

### 03 «Что внутри» — dark bento, first iteration (2026-08-17)

Owner set the block's job: explain what the membership consists of. Visual
concept (my proposal, pending owner's references): dark contrast panel
(ink #16130E, radius 30px) on the light page + bento of 6 tiles with real
artifact miniatures. Tiles: Production-разработка (code) / Работа с
AI-агентами (terminal) / Архитектура проектов (diagram) / Карьера (checklist)
/ Реальная практика (wide, ADR) / Сообщество (chat). Layout: 6-col bento on
desktop, 2 cols at 700–999px, single column on mobile. Owner will send
references; the section will be reworked from them.

Update (2026-08-17, later): owner liked the clay 3D direction. All 6 tiles
now carry generated clay objects (ChatGPT, transparent bg, style-matched to
the hero computer): Production = server, AI-first = robot with "S", Архитектура
= connected modules, Карьера = staircase with flag, Практика = workbench
(wide tile, object right), Сообщество = speech bubbles. Text artifacts (code,
terminal, diagram, checklist, ADR, chat bubbles) removed; their CSS cleaned
up. Assets: `visual/prototypes/assets/tile-*.webp/.png`. Generation prompt
template is fixed for future objects (clay style anchors + isometric 3/4
facing left + transparent background). Eyebrow, lead and tile micro-labels
were removed by owner — only H2 «Что внутри», bold tile titles, descriptions
(15.5–17.5px fluid). Tile title is «Production разработка» (no dash, owner
edit). Tile descriptions after owner pass: AI = harness, скиллы, пайплайны
агентов, проверка работы, решения; Архитектура = бэкенд, фронтенд,
микросервисы, реальные проекты не учебные; Практика = решения, ошибки,
инфраструктура, деплой, практика для production и карьерного роста (no
anglicisms like trade-offs).

### 01 Hero — copy locked (2026-08-17)

- H1: «От разработчика / к Software Engineer.» (two lines, same size, glitch on
  «Software Engineer»).
- Sub (owner's latest edit in the prototype): «Реальные решения и опыт,
  архитектура проектов, AI-first разработка с агентами, разбор production
  кейсов и сообщество.»
- Eyebrow «Private Engineering Access» removed as redundant.
- CTA pair: «Получить доступ» (primary, action still TBD) + «Что внутри».
- Responsive rules settled: object stays right of the text down to 700px
  (columns 1.25fr/0.75fr below 1000px, 1.1fr/0.9fr above), single column below.
  H1 fluid: clamp(30px, 8.4vw, 60px) single-column, clamp(30px, 4.4vw, 52px)
  two-column; both lines nowrap, always 2 lines.

# Coding standards

These standards are normative for the production Astro application. Product, copy, and visual
decisions remain in the sources routed by [`docs/agents/domain.md`](docs/agents/domain.md).

## Structure and content

- Keep `app/src/pages` limited to route composition and metadata. Put reusable page sections in
  `app/src/components`, global tokens/layout in `app/src/styles`, and shared runtime facts in a
  focused module.
- `app/src/config.ts` is the single authority for `TRIBUTE_URL`. Every conversion link imports it;
  do not duplicate the literal URL in components.
- Render the page's meaning and primary navigation as semantic HTML before JavaScript. Scripts add
  enhancement, not access to content or conversion.
- Prototypes, reference captures, and historical playbook artifacts are design evidence only and
  never production imports.
- Do not invent claims, prices, testimonials, metrics, support terms, or product capabilities. Use
  the repository-owned product and copy documents; surface unresolved facts instead of filling them.

## Responsive and interaction behaviour

- Work mobile-first and verify the full composition at 320, 393, 768, and 1440 CSS pixels. Treat
  intermediate widths and horizontal overflow as explicit risks.
- Preserve keyboard access, visible focus, meaningful labels, correct expanded state, Escape
  handling, and focus restoration for interactive controls.
- Respect `prefers-reduced-motion`: all information and final visual state remain present without
  animation. Keep deterministic query states (`?static`, `?faq=open`, `?nav=open`,
  `?glitch=freeze`) working for repeatable review.
- Avoid layout shifts during hover, focus, loading, hydration, or reveal. Reserve the footprint or
  use an overlay when transient UI expands.
- Inline scripts stay small, page-owned, and progressively enhance existing markup. Add a library
  only for a demonstrated interaction that cannot remain clearer and smaller locally.

## Completion

Run `npm run verify --prefix app`, then apply the browser matrix in [`app/QA.md`](app/QA.md) to the
changed surface. Evidence belongs to the issue or pull request; keep only reusable acceptance rules
in the repository.

# Browser acceptance contract

This file defines repeatable acceptance for the production landing. Screenshots, dates, commit
hashes, and individual review results belong to the issue or pull request, not this contract.

## Build gate

From the repository root run:

```bash
npm run verify --prefix app
```

This must complete Astro validation/build and verify the generated canonical metadata, Open Graph,
robots, sitemap, and health endpoint.

## Required viewports

Check the affected composition at:

| Viewport | Purpose |
|---|---|
| 320 px wide | minimum-width stress and overflow |
| 393 × 852 | primary mobile composition |
| 768 × 1024 | tablet/intermediate layout |
| 1440 × 1000 | desktop composition |

Add intermediate checks near changed breakpoints. At every checked width, document width equals the
viewport, text and controls do not overlap, images load with non-zero natural dimensions, and the
appropriate navigation remains available.

## Interaction and accessibility

- Conversion links use the value exported by `src/config.ts`, open safely, and are not dead ends.
- The mobile menu opens and closes by pointer and keyboard, closes with Escape, restores focus, and
  keeps background scrolling controlled.
- FAQ buttons maintain correct `aria-expanded`/`aria-controls` and independent item state.
- Keyboard navigation exposes a visible focus state and follows the visual reading order.
- The accessibility tree contains one meaningful page heading and labelled interactive controls.
- Browser console has no errors or warnings caused by the page.

## Progressive enhancement and motion

- With JavaScript disabled at 393 px, content and conversion remain available, semantic fallback
  navigation is visible, inert enhancement controls are hidden, and no horizontal overflow appears.
- With reduced motion enabled, glitch, reveal, terminal, floating, navigation, CTA, and social
  motion stop while the complete composition remains visible.
- Verify deterministic states `?static`, `?faq=open`, `?nav=open`, and `?glitch=freeze` whenever
  their owning behaviour changes.

## Boundaries

Local QA verifies the configured external destination and link behaviour; it does not complete an
external checkout. Deployment, domain binding, production smoke, and field Core Web Vitals are
separate operational checks. State every relevant boundary not exercised in the handoff.

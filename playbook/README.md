# Landing playbook

This is the current delivery contract for the production landing. The original discovery handoff
is retained as historical evidence in
[`handoff-new-landing-playbook-2026-08-15.md`](handoff-new-landing-playbook-2026-08-15.md); it is not
current task routing.

Current stage: **production maintenance**. Product, conversion event, visual direction, and the
Astro implementation exist. Changes preserve confirmed authority unless the owner explicitly
reopens it.

## Authority

| Concern | Current source |
|---|---|
| Product claims, audience, and scope | [`product/README.md`](../product/README.md) |
| Visible copy and block intent | [`copy/README.md`](../copy/README.md) |
| Visual system, composition, motion, and QA states | [`visual/README.md`](../visual/README.md) |
| Reference cards and local evidence | [`references/README.md`](../references/README.md) |
| Application implementation rules | [`CODING_STANDARDS.md`](../CODING_STANDARDS.md) |
| Reproducible browser acceptance | [`app/QA.md`](../app/QA.md) |

Unknown claims, prices, testimonials, screenshots, and support terms remain explicit; agents never
invent them. A durable product or visual change updates its owning source in the same change.

## Change flow

1. Classify the request against the authority table and read only the owning documents.
2. Preserve the existing direction for ordinary refinements. If the request changes product truth,
   conversion, page structure, or the visual system, make that decision explicit before coding.
3. Implement in the production Astro application. Prototypes and reference assets are evidence,
   never runtime dependencies.
4. Run `npm run verify --prefix app` and the browser acceptance matrix in `app/QA.md` in proportion
   to the changed surface.
5. Record durable rules in their authority and attach transient screenshots/results to the issue or
   pull request. Do not turn `app/QA.md` into a chronological review ledger.

## Owner gates

Owner approval is required to replace the confirmed visual direction, change product claims or the
conversion destination, publish/deploy, or merge. Ordinary implementation and QA inside an already
approved direction do not reopen discovery.

## Definition of Done for UI changes

- confirmed claims and no invented proof;
- every visible conversion action reaches the configured destination without dead ends;
- semantic content remains useful without JavaScript;
- keyboard, focus, contrast, responsive layouts, and reduced motion are checked;
- deterministic QA states still represent interactive states;
- no console errors or horizontal overflow at the required viewports;
- `npm run verify --prefix app` passes and any untested boundary is stated in the handoff.

Production Core Web Vitals are measured from deployed traffic. The application targets LCP ≤ 2.5
s, INP ≤ 200 ms, and CLS ≤ 0.1, but local screenshots do not claim field performance.

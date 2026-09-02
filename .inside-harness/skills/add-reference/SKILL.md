---
name: add-reference
description: Add a visual reference to the collection in references/. Use when the user shares a link to a site or landing, screenshots, a markdown file, a prompt, or a description of a design reference for the Sachkov Inside landing.
---

The user sent a **reference**. Process it — fetch, screenshot, analyse — so it is ready to feed the visual direction, not just bookmarked.

The collection lives in `references/`: cards in `references/items/`, assets in `references/assets/`, tag taxonomy and index in `references/README.md`. Read `references/README.md` first — it is the single source of truth for the card template and tags.

## Steps

1. **Identify the input.** Link, screenshot(s), markdown file, prompt, or text description — possibly combined. Any comment the user sent with it goes into the card verbatim, in its original language.

2. **Pick the name.** Next `NNN` number from `references/items/` plus a short lowercase slug naming the essence (`003-linear-hero`).

3. **Gather material**, per input type:
   - **Link:** use the runtime's available browser or page-fetch capability. Prefer the repository's
     managed `playwright-cli` skill for repeatable desktop (1440px) and mobile (393px) screenshots.
     Save `NNN-slug-desktop.png`, `NNN-slug-mobile.png`, and any focused section captures in
     `references/assets/`. Inspect saved images with the runtime's available image viewer. Ask
     before installing browser tooling or dependencies.
   - **Screenshots:** copy the files into `references/assets/NNN-slug-*.png` and inspect every image
     with the runtime's available image viewer.
   - **Markdown / prompt file:** copy into `references/assets/` under the same `NNN-slug` prefix.
4. **Write the card** `references/items/NNN-slug.md` from the template in `references/README.md`, including the playbook fields: the reference's function, the one principle to take, what must not be copied, and license constraints. The analysis must be concrete: hex colors where visible, font names or precise descriptions, grid, density, named techniques. Done means every template section is filled from what was actually seen. "Takeaways for Inside" is a hypothesis weighed against the product character in `product/README.md`.
5. **Tag** from the taxonomy in `references/README.md`. A new tag is allowed only when no existing one covers the trait — then add it to the taxonomy in the same edit.
6. **Update the index** in `references/README.md`.
7. **Report briefly:** saved paths, tags, 2–3 key findings.

## Boundaries

- State what's unavailable: a login wall or unrenderable page goes into the card as-is, followed by a request to the user for screenshots. The analysis covers only what was actually seen.
- One run — one reference. Several links or screenshot sets get separate cards and numbers.
- The card records observations; decisions for the visual direction land in `visual/README.md` only when the user confirms them.

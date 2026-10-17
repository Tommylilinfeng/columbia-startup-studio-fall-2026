# 5 PPL — Homework 5: MVP doc, homepage, and landing pages

Product: **UnlockDrill**. One practice question before you scroll.
Product repository: https://github.com/Tommylilinfeng/unlockdrill (code, question banks, brand docs, deploy workflow).

## Live pages

All pages are deployed from `main` by GitHub Actions to GitHub Pages. A purchased domain is not yet attached (see "Open items").

| Page | URL | Audience | Value prop |
| --- | --- | --- | --- |
| Homepage | https://tommylilinfeng.github.io/unlockdrill/ | Adults 18+ preparing for a standardized test who keep postponing practice | One question before you scroll |
| Landing 1 | https://tommylilinfeng.github.io/unlockdrill/for/scrollers | People who meant to study and opened Instagram instead (persona Maya, the tired starter) | A smaller first step |
| Landing 2 | https://tommylilinfeng.github.io/unlockdrill/for/blocker-skeptics | People who tried Screen Time or an app blocker and turned it off (persona Jordan, the blocker skeptic) | Control, not a lock: skip is always on the screen |
| Landing 3 | https://tommylilinfeng.github.io/unlockdrill/for/reviewers | People who already practice but repeat the same mistakes (persona Casey, the purposeful reviewer) | Know why you got it wrong |
| Thank-you | https://tommylilinfeng.github.io/unlockdrill/thanks | After signup; fires the `signup` event | — |

Every page has one call to action and an email signup form. Signups are stored in Supabase (table `signups`, insert-only from the browser) once the project's keys are set as GitHub Variables; until then the form completes and stores locally so the flow can be tested.

Style: the HW4 style guide and logo (`docs/style_guide.md`, `public/logo/`) are applied through CSS tokens. Imagery is the product's own question UI and the original vector mark; no stock photography.

## MVP doc

See [mvp_doc.md](mvp_doc.md).

## Open items (as of this PR)

- Custom domain: not purchased yet. The GitHub Pages URL is live and public; the build already supports moving to a root domain by changing one variable.
- Google Analytics property and Supabase project: created by the team, keys added as repository Variables. The code paths are in place and tested with local fallbacks.
- Analytics Academy: not started yet (noted here honestly; the HW6 README tracks it).

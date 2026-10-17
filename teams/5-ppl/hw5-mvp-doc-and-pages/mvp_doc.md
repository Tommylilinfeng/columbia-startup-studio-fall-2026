# UnlockDrill — MVP doc

**Team:** 5 PPL (Linfeng Li, Yicheng Ying, Cody Wang, Arjun Joshi, Kushaan Vardhan)
**Date:** October 2026 · **Status:** v1 for the October 23 midterm. Items marked *proposed* need a team decision.

## 1. What we're building

**Problem.** People who intend to study for a standardized test lose the moment to reflexive scrolling. The barrier is starting, not ability: "The hardest part is just sitting down to start. Once I pick up my phone, hours are gone." (I03). Blockers do not survive contact with the user: "I just tap ignore and keep scrolling." (I04). Evidence: [brand position](../hw4-synthesis-brand-position/brand_position.md), [interview notes](../hw3-interviews/interviews.md), [Reddit research](../hw4-synthesis-brand-position/reddit_research/).

**Who it's for.** Adults 18 and over preparing for a standardized test, who study in the gaps of a normal week and reach for Instagram, TikTok, or YouTube when they meant to practice. *Proposed:* the first content bank is SAT (the exam our HW3 interviews covered) with an 18+ gate; a GRE bank exists in the repo and the team may switch the launch exam to GRE, whose takers are adults by default. The course bars collecting data from minors; the product's copy, privacy page, and signup form state 18+ only.

**Core flow: user, action, value.**
A test taker opens the app they chose (say, Instagram). One short question appears first. They answer it, read a one-line explanation, and are sent back into Instagram. The value is a start they actually made, with the "why" attached, at a moment they would otherwise have lost.

## 2. MVP features

- iOS integration through the Shortcuts app: "When *app* is opened → Open URL" sends the user to `/q?app=…` with no App Store app and no Screen Time entitlement.
- Guided setup page (`/setup`): choose the app and frequency, copy the link, seven steps with screenshots to come.
- One-question interstitial (`/q`): question, four or five choices, instant verdict, one-line explanation, "Back to *app*".
- Skip, always visible at the top. Pause for an hour or for the day, always visible below the question.
- Frequency control: every open, every third open, at most hourly, once a day.
- Original question banks (SAT: 17 items, GRE: 8 items) with a validator that runs in CI.
- Homepage plus three landing pages with email capture, thank-you page, GA4 page views, `signup` key event, and practice events (`shown`, `answered`, `skipped`, `paused`, `returned`).
- On-device settings only; practice events carry a random device id, not an identity.

## 3. What comes later

1. **Real-iPhone verification of the Shortcuts automation across iOS versions.** The whole product rests on it; we claim compatibility only after testing.
2. **Question bank to 150+ items per exam, reviewed by a second person.** Repeats kill the value; variety is the product.
3. **Error journal (the HW2 "ErrorJournal" idea).** After a miss, one tap: careless, concept, or time. Weekly pattern. Interviewees asked for the why, not the letter (I08, Casey persona).
4. **Welcome and day-3 emails.** "Did you set it up?" is where we expect to lose people.
5. **Android.** Intent-based automation (e.g., via Tasker or MacroDroid) is possible but a different guide.
6. **Topic focus.** Let the user pick sections. R4: "I only need to work on math."
7. **Spaced repeats.** Bring back similar questions, not the same one.

## 4. What's cut and what's faked

**Cut from the MVP:** accounts and sign-in, streaks and badges, any feed, score prediction, tutoring or chat, a native app, Android, payments, topic selection, social features.

**Faked (Wizard of Oz):**
- Welcome email: sent by hand from the team inbox until Resend is wired up.
- Question review: a teammate reads new items by hand before they ship; there is no automated review.
- "We'll notify you when it's ready": the notification is a manual email from the team.
- Demo-day phones: we pre-create the Shortcuts automation on team phones; the audience sees the real flow, not the two-minute setup.

Nothing in the live demo is a mock-up: the question flow, settings, signup, and analytics events run for real.

## 5. Stack and services

| Layer | Choice | Cost |
| --- | --- | --- |
| Framework | Vite + React + TypeScript, client-side routing | $0 |
| Coding agent | Claude Code, with `AGENTS.md` and three persona judges in `.claude/agents/` | covered by team plans |
| Hosting | GitHub Pages via Actions (now); custom domain on the same build later | $0; domain about $12/yr |
| Analytics | Google Analytics 4 | $0 |
| Database | Supabase free tier: `signups`, `practice_events`, insert-only RLS | $0 up to 500 MB |
| Email | Resend free tier for the welcome email | $0 up to 3,000/month |
| Sign-in, payments, AI model at runtime | none | $0 |

Total recurring cost today: $0. First paid item: the domain.

## 6. How we'll know it works

**Primary metric:** email signups per landing page (the `signup` key event), which also tells us which value prop pulls.
**Product metric:** of questions shown to people who completed setup, the share answered rather than skipped, and whether they are still answering on day 3.

*Proposed* decision rule for October 23 → November 6: at least 30 signups across the pages, at least 10 people who complete the Shortcuts setup, and an answer rate above 30% among them. Below that, the mechanism is not pulling and we revisit the moment (the open) or the unit (one question).

## 7. Risks and open questions

- **iOS behavior.** If a future iOS version adds a confirmation to app-open automations, the friction may kill the habit. Mitigation: test on every beta; keep the web flow fast enough that even a tap-through stays under 20 seconds.
- **Skip becomes the default.** Our position is control, not a lock. If nearly everyone skips, the offer is wrong, not the user. The skip rate is a first-class metric.
- **Audience.** SAT content and adult-only data collection sit awkwardly together. Decision needed: GRE first, or SAT with an 18+ gate. The code supports both with one variable.
- **Content quality.** A wrong explanation destroys trust faster than a missing feature. Every item gets a second reader.
- **Distribution.** r/Sat and r/GRE moderate self-promotion. Posts must be useful first (a question with its explanation), link second.
- **Return deep link.** `instagram://` and friends are undocumented schemes. If one breaks, we fall back to the web URL; the user loses nothing but a second.

## 8. Roles

*Proposed from the PR history and interview load; the team confirms names before the midterm.*

| Area | Owner | Backup |
| --- | --- | --- |
| Product repo, question flow, deploy | Linfeng Li | Kushaan Vardhan |
| Landing pages and copy | Arjun Joshi | Linfeng Li |
| Question banks and review | Yicheng Ying | Cody Wang |
| Analytics setup, Supabase, email | Kushaan Vardhan | Linfeng Li |
| Traffic this week (posts, communities) | Cody Wang | Arjun Joshi |
| Midterm deck and demo phone | all present; Linfeng demos, Arjun presents problem, Cody presents audience, Yicheng solution, Kushaan metrics | — |

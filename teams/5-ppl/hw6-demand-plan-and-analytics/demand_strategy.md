# UnlockDrill — Demand strategy, October 19 to December 18, 2026

**Team:** 5 PPL · **Goal:** 100 email signups by Demo Day (December 18) and at least 20 people who complete the iPhone setup.
**Status:** v1 draft for the October 23 midterm. Names marked *proposed* rotate once the team confirms. Post links are added to the table as each post goes out.

## 1. Who owns traffic, by week

| Week of | Class | Traffic owner | Backup | Focus that week |
| --- | --- | --- | --- | --- |
| Oct 19 | 7, midterm | Cody Wang *(proposed)* | Arjun Joshi | First 3 Reddit posts, Columbia groups, class demo |
| Oct 26 | 8 | Arjun Joshi | Cody Wang | Blog post 1, Reddit follow-ups, replies in threads |
| Nov 2 | 9 | Kushaan Vardhan | Linfeng Li | Email 2 and 3 to the list, LinkedIn article |
| Nov 9 | 10 | Yicheng Ying | Kushaan Vardhan | Blog post 2, GRE/SAT Discord servers |
| Nov 16 | 11 | Linfeng Li | Yicheng Ying | AMA-style post: what we learned from 12 interviews |
| Nov 23 | 12, Thanksgiving | Cody Wang | Arjun Joshi | Light week: one post, referral nudge email |
| Nov 30 | 13 | Arjun Joshi | Linfeng Li | Blog post 3, December test-date angle |
| Dec 7 | 14 | Kushaan Vardhan | Cody Wang | Blog post 4, "early access is open" email |
| Dec 14 | Demo Day | all | — | Final push, Demo Day live demo |

Rule: the owner posts, replies to every comment within a day, and updates the post table below with links and UTMs.

## 2. Top communities

Reach estimates are to be filled from each community's member count on the day we post; we do not guess them here. Expected views per post are conservative.

| Community | Why it fits | Rules to respect | Expected views per post |
| --- | --- | --- | --- |
| r/Sat | Our interviews and Reddit research (R1, R2, R4) came from here; the "studying but scrolling" thread is the problem in users' own words | No self-promotion posts; value-first posts with a link in a comment or profile | 500–2,000 |
| r/GRE | Adult test takers by default; same starting-friction problem | Similar; weekly "what are you using" threads allow tool mentions | 300–1,500 |
| r/digitalminimalism and r/nosurf | Our "blocker skeptic" audience (R3); people who have tried and dropped blockers | Products are discussed when framed as an experiment, not an ad | 500–3,000 |
| r/GetStudying, r/productivity | Broad; "how do I stop scrolling when I should study" is a recurring post | Lower fit, higher volume | 200–1,000 |
| Columbia groups: GRE prep GroupMe/Discord, SEAS senior channels, class Slack | Warm audience, adults, easy to ask for setup feedback | Ask admins first | 50–200 each, high conversion |
| Discord: SAT/GRE prep servers | Real-time; good for "try this one question" | Read each server's #promo rules | 100–500 |

## 3. Social posting schedule and first posts

Cadence: two posts a week from the traffic owner, plus replies. Every link carries lowercase UTMs: `utm_source=<community>&utm_medium=social&utm_campaign=5ppl_unlockdrill_oct2026&utm_content=<post-id>`.

| # | When | Where | Post (format) | Links to | UTM content | Link to post |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Oct 19–20 | r/Sat | "I kept opening Instagram instead of studying, so I put one SAT question in front of it. Here's the question and the why." Value-first: the question, the explanation, one line on the setup | /for/scrollers | post1 | *(add)* |
| 2 | Oct 20–21 | r/digitalminimalism | "Screen Time never stopped me. An experiment: one question before the app opens, skip always allowed. What's your escape hatch?" Asks for their bypass stories | /for/blocker-skeptics | post2 | *(add)* |
| 3 | Oct 21–22 | r/GRE | "A one-line explanation beats the answer key: an example from our question bank, and why we built it that way" | /for/reviewers | post3 | *(add)* |
| 4 | Oct 26 week | Columbia GRE/SEAS groups | "Built in Startup Studio, looking for 10 iPhone testers" | /setup | post4 | *(add)* |
| 5 | Nov 16 week | r/Sat or r/GRE | AMA: "I'm building UnlockDrill for people who scroll instead of studying. Here's what I learned interviewing 12 test takers." | / | ama1 | *(add)* |

## 4. Blog posting schedule

Published on the product site (owning the traffic), cross-posted to Medium and LinkedIn. Four posts in the remaining weeks, one every two weeks. Candidate list by article type from the class 6 slides:

**Problem-focused**
1. Five moments test takers lose to their phone, from 12 interviews *(Oct 26)*
2. Why "just use Screen Time" does not work for anyone we talked to

**Founder journey**
3. What 12 interviews taught us about starting, not finishing *(Nov 9)*
4. The idea we almost built instead: ErrorJournal

**Solution explainer**
5. One question before you scroll: how UnlockDrill uses an iPhone automation instead of a blocker *(Nov 30)*
6. What we fake on purpose and what is real in our MVP

**Tactical advice**
7. A two-minute Shortcuts setup that puts anything in front of Instagram *(Dec 7)*
8. Ten-second explanations: how to write an answer explanation you will actually read

Dates in parentheses are the four we commit to; the rest are the backlog.

## 5. Email strategy

List: signups from the homepage and landing pages, stored in Supabase. Sending: Resend free tier once set up; until then the welcome email is sent by hand from the team inbox (a named Wizard of Oz step in the MVP doc).

Lifecycle, anchored on signup date, following the four-email playbook:

| Email | When | Content |
| --- | --- | --- |
| 1. Welcome | Immediately, automated | "You're on the list." One question back: which app would you attach it to, and which exam? |
| 2. Founder story | +3 days | Why we built this: the interview moment that changed the idea (I04's "I just tap ignore") |
| 3. Progress update | +7 days | A screenshot of the question flow, invite to try the demo link |
| 4. Early access | When setup is verified on real phones | "You're first": the setup guide, ask for one reply after three days of use |

Feature-usage branch: anyone who completes setup (first `practice_shown` event) gets a day-3 "still answering?" note instead of email 3. Referral: the thank-you page will carry a share link (`/?ref=<code>`) once we can track it; the offer is "share with a friend, both get early access".

## 6. Back-of-napkin math

Target: 100 signups in 9 weeks.

| Source | Posts / touches | Views each | Views | Conversion | Signups |
| --- | --- | --- | --- | --- | --- |
| Reddit posts (r/Sat, r/GRE, r/digitalminimalism, r/nosurf, r/GetStudying) | 18 | 800 | 14,400 | 0.5% | 72 |
| Blog + Medium + LinkedIn | 4 posts, 3 channels | 150 | 1,800 | 1% | 18 |
| Columbia groups and Discord | 10 touches | 100 | 1,000 | 5% | 50 |
| Referrals | 20% of signups refer one friend | | | | +20% |
| **Total** | | | about 17,000 | | **about 140 before referrals, 100 with half the Reddit posts underperforming** |

Reddit conversion is set below 1% because posts link in comments, not titles. If the first three posts come in under 300 views each, we shift effort to Columbia groups and Discord, where conversion is higher and the audience is adult by default. We update this table with real numbers after the first week.

## 7. Analytics on every page

Google Analytics 4 is wired into the product site: page views on every route, `signup` fired on the thank-you page (to be marked a key event in the GA property), and `practice_shown / answered / skipped / paused / returned` from the question flow. The measurement id is injected at build time from a repository variable. Realtime check and the Analytics Academy 101/102 completion are tracked below.

- [ ] GA4 property created and `VITE_GA_ID` set *(owner: Kushaan, proposed)*
- [ ] `signup` marked as a key event
- [ ] Realtime report shows a visit from a UTM link
- [ ] Analytics Academy 101 started · 102 started

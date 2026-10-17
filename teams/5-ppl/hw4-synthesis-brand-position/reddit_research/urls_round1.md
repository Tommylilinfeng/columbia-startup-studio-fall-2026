# Reddit research: round 1 links

Workflow from class 4: the agent lists `.json` links, a **person** opens each in a logged-in browser at a normal pace and saves the page (File > Save Page As, keep the `.json` name) into `reddit_corpus/raw/`. Then run `scripts/reddit_json_ingest.py --raw ./reddit_corpus/raw --out ./reddit_corpus/normalized --corpus ./reddit_corpus/normalized` and the agent reads the normalized files and lists round 2. Raw pages are not committed.

Problem space: people who intend to study for a test and lose the moment to scrolling; what they tried (blockers, Screen Time), why it failed, and what a "small start" looks like in their words. Target user: adults preparing for the SAT or GRE.

## A. Re-save the five threads already cited in HW4 (so quotes are backed by saved pages)

1. https://www.reddit.com/r/Sat/comments/1s9xuk7.json
2. https://www.reddit.com/r/Sat/comments/k3og1a.json
3. https://www.reddit.com/r/digitalminimalism/comments/1wmj8j7.json
4. https://www.reddit.com/r/Sat/comments/1bfkrz9.json
5. https://www.reddit.com/r/UPSC/comments/1wn57vb.json

## B. Discovery searches (each returns up to 25 threads; save the search page, then pick threads from it for round 2)

6. https://www.reddit.com/r/Sat/search.json?q=scrolling+phone+studying&restrict_sr=1&sort=top&t=year
7. https://www.reddit.com/r/Sat/search.json?q=can%27t+start+studying&restrict_sr=1&sort=top&t=year
8. https://www.reddit.com/r/Sat/search.json?q=screen+time+app+blocker&restrict_sr=1&sort=top&t=all
9. https://www.reddit.com/r/GRE/search.json?q=procrastinating+phone&restrict_sr=1&sort=top&t=year
10. https://www.reddit.com/r/GRE/search.json?q=study+while+working+full+time&restrict_sr=1&sort=top&t=year
11. https://www.reddit.com/r/GRE/search.json?q=one+question+a+day&restrict_sr=1&sort=top&t=all
12. https://www.reddit.com/r/digitalminimalism/search.json?q=ignore+limit+screen+time&restrict_sr=1&sort=top&t=year
13. https://www.reddit.com/r/nosurf/search.json?q=app+blocker+bypass&restrict_sr=1&sort=top&t=year
14. https://www.reddit.com/r/GetStudying/search.json?q=open+instagram+instead+of+studying&restrict_sr=1&sort=top&t=year
15. https://www.reddit.com/r/productivity/search.json?q=one+small+task+to+start&restrict_sr=1&sort=top&t=year
16. https://www.reddit.com/r/Sat/search.json?q=explanation+wrong+answer+why&restrict_sr=1&sort=top&t=year
17. https://www.reddit.com/r/GRE/search.json?q=error+log+mistakes&restrict_sr=1&sort=top&t=all

Please open each link in your browser, save the page into `reddit_corpus/raw/` with a `.json` name, and tell the agent when you're done. Open a few at a time; opening dozens at once gets rate limited and the saved pages come back empty. If a link shows an access-denied page from the network, open the normal thread page first, then the `.json` link again.

## Where this goes

After two or three rounds (30 to 100 saved threads in total): `reddit_research_summary.md` (agent write-up with linked, verbatim quotes), `quotes_used.md` (3 to 5 quotes, each with its link and where it was used), and `coverage.md`. These replace the five-thread scan noted in the HW4 README.

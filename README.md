# TakeMeter

> ### 👋 Start here
>
> **New to this repo? Read [RUNNING.md](RUNNING.md) first** — setup, the
> notebook, the baseline, and what to do when something breaks.
>
> Once `python test.py` passes:
>
> ```bash
> head -5 data/practice_labels.csv     # the shape your labels.csv needs
> ```
>
> Then open `takemeter.ipynb` **in this folder** — in VS Code, or with
> `jupyter notebook` if you prefer. Pick the kernel: the `.venv` inside this
> project. Run section 1, which reports the hardware you'll be training on.
> Everything else waits until you have data.
>
> Nothing to upload, nothing to connect, no accounts and no keys. The notebook
> runs on your machine and writes next to your code.
>
> **The rest of this file is your submission.** Fill it in as you go.

---

<!-- ─────────────────────────────────────────────────────────────────────────
     HOW TO USE THIS FILE

     Unit 5 asks for the first five sections. Unit 6 adds the five below them.

     Everything is pasted as TEXT. No screenshots, no images.

     ⚠️ The confusion matrix especially. The notebook prints one as a markdown
     table, ready to copy. A screenshot of a matrix earns nothing. Paste the
     table.
     ───────────────────────────────────────────────────────────────────────── -->

<!-- ═══════════════════════ UNIT 5 — THE BUILD ═══════════════════════ -->

## Milestone 1 Notes

# Community: r/pcgaming 

# Link to community: https://www.reddit.com/r/pcgaming/

# Candidate distinctions

1. News posts: The title is usually the headline of an article, and the post body contains a link to an article on another website.

2. Game trailers/ads: These usually contain an embedded video, and the title includes the game name and “Trailer.” Some announce that a game is available now and link to its store page.

3. Self-written posts: These contain mostly original text and cover a variety of topics. Some also include pictures.

4. Advertisements: These posts promote a company or product, sometimes unrelated to the subreddit’s main topic. Reddit marks some posts with an “Ad” label next to the username. Examples I noticed include posts from u/Netflix, u/Depop, and u/farmers insurance.

---

## What This Does

<!-- Your community, and what your classifier sorts posts into. Three or four
     sentences. -->



---

## Label Taxonomy

<!-- Each label: a one-sentence definition and two real examples from your
     reading. Then your decision rule for the hardest boundary.

     The decision rule is worth a point on its own and it's the thing most
     people leave out. Every taxonomy has a hardest boundary. Name yours. -->

### `Gaming News`

**Definition: Posts primarily sharing or discussing external news articles about video games, gaming companies, or the gaming industry.**

**Example 1: https://www.reddit.com/r/pcgaming/comments/1x5taw3/epic_games_vibe_coded_its_new_store_and_openly/**


> Epic Games vibe coded its new store and openly admits it while taking jabs at Steam and Gabe's yachts

https://www.destructoid.com/epic-games-store-ai-vibe-coded/

Because making a functional, feature-rich software is too big of a deal. They even said "programming is hard." Lol, lmao even

**Example 2: https://www.reddit.com/r/pcgaming/comments/1x5y25k/jeff_kaplan_was_an_industry_icon_now_peers_ignore/**

> Jeff Kaplan Was An Industry Icon, Now Peers Ignore His Emails: Ex-Overwatch Director Talks “Humbling” Reality Of Indie Dev

https://www.gamespot.com/articles/jeff-kaplan-was-an-industry-icon-now-peers-ignore-his-emails-ex-overwatch-director-talks-humbling-reality-of-indie-dev/

### `Game Trailers/Advertisements`

**Definition: Posts primarily promoting a game or its release, including official trailers, promotional videos, and announcements that a game is available.**

**Example 1: https://www.reddit.com/r/pcgaming/comments/1x51zgg/valor_mortis_is_available_now_on_steam/**

> Valor Mortis is available now on Steam

https://store.steampowered.com/app/2828710/Valor_Mortis/

**Example 2: https://www.reddit.com/r/pcgaming/comments/1x5zqat/battlefield_6_game_of_the_year_edition_trailer/**

> Battlefield 6: Game of the Year Edition Trailer

https://www.youtube.com/watch?v=PeHxMayIpaI

     >Go all-in on All-Out Warfare.

     >The Battlefield 6 Game of the Year Edition delivers the most complete Battlefield experience.

     >Fight across land, air, and sea on 20* maps with 70+ weapons, 30+ vehicles, and 700K+ Portal experiences.

     >Hit the ground running with the Ultimate Shortcut Kit, giving you faster access to fully progressed weapons and attachments across all four classes, plus one season of Battlefield Pro.

     >The Game of the Year Edition also includes the new Trusted Reserve Pax Support Soldier Skin and the Phantom Pack, featuring four soldier skins, two weapon packages, XP boosts, and more.

     >*19 maps available at launch. The 20th map is planned for release on Nov. 10.

### `Self-Written`

**Definition: Posts primarily consisting of original text written by the Reddit user, rather than primarily sharing an external article or promotional material.**

**Example 1: https://www.reddit.com/r/pcgaming/comments/1x61zme/heart_of_the_machine/**

>Heart of the Machine

Just wanted to share this very unique game as I was impressed. I just finished the Prologue and a few turns in Chapter 1. Its very engaging and the graphics gives me an isometric Cyberpunk 2077 vibe. RPG/some building/4X turn-based but very story-based so that's a good change for me. It seems very deep so far and has lit a new fire on my gaming as I have been feeling burnt-out for a while. Also on sale on Steam. Let me know what you think!

**Example 2: https://www.reddit.com/r/pcgaming/comments/1x1t7os/nearly_7000_early_access_games_on_steam_havent/**

>Nearly 7,000 Early Access games on Steam haven't been updated in over a year

[image]

Edit for clarity: these numbers are from a study I put together from public Steam data. The ~7,000 in the title are all games in Early Access on Steam right now that have Steam's "no update in over a year" note, most of them tiny games with almost no reviews. The chart is something else: what happened to the 10,141 bigger games (10+ reviews) that entered EA between 2013 and 2023. Most of those reached 1.0 and left Early Access, which is exactly why the store shelf looks so much worse than the outcomes.

Early Access is a subject that moves people's emotions, so I wanted to check what actually happens to these games. Mostly the numbers matched what I assumed. The one thing I did not expect is that the majority actually get finished.

- On 26 September 2026, 6,989 of the 12,320 Early Access games on Steam carried Steam's own note that the developers' last update was over a year ago.

- Of the 10,141 games with at least 10 reviews that entered Early Access between 2013 and 2023, 26% were still in Early Access with no update for 12+ months, and 7% were removed from sale while still in Early Access.

- After three years without a 1.0, only about one in five still got there within the next five years.

- About seven in ten store pages that give a time estimate say a year or less. Of the games with 10+ reviews that entered at least a year before the data date, 31% reached full release within a year.

- But of those same 10,141 games, 61% had reached full release by 26 September 2026 (51% counting every game, however few reviews). Finished games leave the Early Access list and most stalled ones stay on it, which is why the store looks worse than the outcomes.

- 21 games are still being updated after more than ten years in Early Access, including Project Zomboid, BeamNG.drive and Universe Sandbox.

The data only shows what happened to the games. It cannot see sales or why developers stopped.

For me, Early Access is both a boon and a bane for the industry. Some amazing games have become truly big by seriously lifting off during EA (e.g. Valheim) - other games have been literally just a cash grab and failures. Curious where you all stand.

### The hardest boundary

Post: https://www.reddit.com/r/pcgaming/comments/1x5bj88/valve_index_sunset/

Valve Index Sunset

https://store.steampowered.com/hardware/valveindex

**Which two labels: `Gaming News` and `Game Trailers/Advertisements`**

Why: The post announces that the Valve Index is no longer being produced, which would count as gaming news. However, it links to Valve's official store page, where remaining hardware is available for purchase, meaning it could also count as an advertisement.

**The decision rule I used every time: If a post's primary purpose is to report a development or event in the gaming industry, it is Gaming News, even if it links to an official store page.  If its primary purpose is to promote a game, trailer, or release, it is Game Trailers/Advertisements, even if it includes factual information.**
<!-- e.g. "If the post names a specific checkable fact, it's `analysis`, even
     if the tone is heated." -->



---

## The Dataset

<!-- Where you collected from, how you labelled, your counts, and three hard
     cases. -->

**Where the posts came from:**

**How I labelled them:** <!-- Cold first? Pre-labelled with AI and corrected?
Say so plainly — the disclosure is required, not penalised. -->

**Counts per label:**

| Label | Count | Share |
|---|---|---|
|  |  |  |
|  |  |  |
|  |  |  |
| **Total** |  | 100% |

**Three hard cases**

<!-- Any post that made you pause: what it was, which two labels it could have
     been, and what you chose. These are worth more than the easy 190. -->

**1.**
> *The post:*
>
> *Could have been:*
>
> *I chose, because:*

**2.**
> *The post:*
>
> *Could have been:*
>
> *I chose, because:*

**3.**
> *The post:*
>
> *Could have been:*
>
> *I chose, because:*

---

## The Training Run

<!-- Your starting model, your settings, and anything you changed and why. -->

**Base model:**

**Settings:** <!-- epochs, learning rate, batch size, seed -->

**Anything I changed from the defaults, and why:**

**Split sizes:** <!-- train / val / test, and per-label counts in the test
split. If a label had fewer than about 8 in test, say so — it explains a lot
of next unit's variance. -->



---

## How I Used AI

<!-- Two specific moments — what you asked, what came back, what you changed.

     ⚠️ Plus disclosure of any pre-labelling. If you had a model pre-label a
     batch and then read and corrected every one, say that. It's an allowed
     workflow and disclosing it costs you nothing. Not disclosing it is the
     problem. -->

**Moment 1**

- *What I asked for:*
- *What came back:*
- *What I changed:*

**Moment 2**

- *What I asked for:*
- *What came back:*
- *What I changed:*

**Pre-labelling disclosure:**

<!-- ═══════════════════════ UNIT 6 — THE TEST ═══════════════════════

     Don't fill these in during unit 5.
     ═══════════════════════════════════════════════════════════════════ -->

---

## Baseline vs. Trained

<!-- Both models on the same posts. `python baseline.py --trained results.json`
     prints this table for you. -->

| Measure | Baseline | Trained | Difference |
|---|---|---|---|
| Overall accuracy |  |  |  |
| Macro F1 |  |  |  |
| F1 — `label_one` |  |  |  |
| F1 — `label_two` |  |  |  |

**What I predicted before I looked:**
<!-- Milestone 1 asks you to write this BEFORE seeing the trained numbers. A
     prediction made afterwards isn't one. -->

**What the gap actually means:**
<!-- If the baseline matched your trained model, your fine-tuning added
     nothing — and that is a real finding, not a failure. Say it plainly. -->



---

## Run Log — Before

<!-- Five criteria across three seeds. The notebook's section 6 prints the
     spread table; the Target and Verdict columns are yours. -->

| Criterion | Target | Seed 42 | Seed 7 | Seed 2024 | Verdict |
|---|---|---|---|---|---|
| 1.  |  |  |  |  |  |
| 2.  |  |  |  |  |  |
| 3.  |  |  |  |  |  |
| 4.  |  |  |  |  |  |
| 5.  |  |  |  |  |  |

### Confusion matrix

<!-- ⚠️ TYPED AS A MARKDOWN TABLE. The notebook prints one ready to paste.
     An image of a matrix earns nothing. -->

| true \ predicted |  |  |  |
|---|---|---|---|
| **** |  |  |  |
| **** |  |  |  |
| **** |  |  |  |

**My biggest off-diagonal number, and what it means:**
<!-- Not "the model made mistakes" — WHICH boundary it didn't learn, and which
     direction. "7 real analysis posts were called hot_take and only 3 went the
     other way" is a direction, not just an error rate. -->



---

## Verdicts and Diagnoses

<!-- MET or MISSED against LAST UNIT's target. The target has to hold across
     all three seeds, not turn up sometimes. -->

| # | Criterion | Target | Verdict | How I decided |
|---|---|---|---|---|
| 1 |  |  |  |  |
| 2 |  |  |  |  |
| 3 |  |  |  |  |
| 4 |  |  |  |  |
| 5 |  |  |  |  |

**Diagnoses**

<!-- For each miss: the cause, and how you know. The four common causes are:
     too few examples for a label, a boundary you applied inconsistently, a
     genuinely hard label pair, and a task the model can't reach from this
     much data.

     ⚠️ Use your agreement report as evidence. It is the only instrument you
     have that can tell a LABELLING problem from a MODEL problem, and this
     section is graded on whether you used it that way. -->



---

## Agreement Report

<!-- Your rate against the staff set, and every disagreement adjudicated.

     Remember you labelled these 30 under the STAFF taxonomy in
     data/staff_taxonomy.md, not your own — so every argument below is made
     from those definitions and those decision rules. -->

**Agreement rate:** ___ / 30 = ___%

<!-- Nobody grades this number. A 60% who argues every disagreement from the
     stated rules beats a 95% who wrote "staff was right" nine times. Several
     of the 30 were chosen because they're genuinely ambiguous — you should be
     winning some of these. -->

**Disagreements**

<!-- Three lines each: the post, both labels, and who you think is right and
     why — grounded in the staff definitions you were both applying.

     Then sort each into one of three piles:
       (a) the rule covered it and I applied it loosely → a consistency problem
       (b) the rule genuinely doesn't say               → a gap in the definitions
       (c) the rule is ambiguous here and my reading is defensible → argue it.
           This is a legitimate win.

     Pile (a) is the one that matters most for your diagnosis: if you applied a
     written rule two different ways on 30 posts, that is direct evidence about
     what you did across your own 200. -->

**1.**
> *The post:*
>
> *Staff said / I said:*
>
> *My call, and why:*
>
> *Which pile:*

**2.**
> *The post:*
>
> *Staff said / I said:*
>
> *My call, and why:*
>
> *Which pile:*

**What the pattern in my disagreements tells me:**



---

## The Improvement

**What I changed:**

**Which diagnosis pointed at it:**

### Run Log — After

| Criterion | Target | Seed 42 | Seed 7 | Seed 2024 | Verdict |
|---|---|---|---|---|---|
| 1.  |  |  |  |  |  |
| 2.  |  |  |  |  |  |
| 3.  |  |  |  |  |  |
| 4.  |  |  |  |  |  |
| 5.  |  |  |  |  |  |

**Did it help, and how do I know:**

<!-- If it didn't, say so. Relabelling that didn't help is a genuinely
     interesting result and earns full credit. -->



---

## What's Still Broken

<!-- For each criterion still missed: what you'd do, and why you stopped. -->



**The gap between what I meant my labels to capture and what the model
learned:**
<!-- Two sentences. Your confusion matrix is the evidence. -->



<!-- ═════════════════════════════════════════════════════════════════════

     SUBMISSION CHECKLIST — unit 5

       [ ] criteria.md has five numbered criteria, each naming a NUMBER
       [ ] Each has a reason underneath tied to your data or taxonomy
       [ ] labels.csv: at least 150 rows, text/label/note, ONE file not split
       [ ] No label above 70%
       [ ] All five unit 5 sections have real content
       [ ] Label Taxonomy includes the decision rule for your hardest boundary
       [ ] The Dataset includes three hard cases
       [ ] results.json and test_split.csv committed (the notebook does this)
       [ ] At least four new commits
       [ ] Repository URL submitted — WRITE IT DOWN

     SUBMISSION CHECKLIST — unit 6

       [ ] Baseline vs. Trained table, with your prediction written beforehand
       [ ] Run Log — Before, five criteria across three seeds
       [ ] Confusion matrix TYPED AS A MARKDOWN TABLE
       [ ] A verdict on every criterion
       [ ] A diagnosis for every miss, using the agreement report as evidence
       [ ] Agreement Report with every disagreement adjudicated
       [ ] One improvement, with Run Log — After
       [ ] What's Still Broken
       [ ] results_three_seeds_before.json, results_three_seeds_after.json,
           baseline_results.json and
           agreement_results.json committed
       [ ] At least four new commits
       [ ] The SAME repository URL as last unit

     Do not delete and recreate this repository.
     ═════════════════════════════════════════════════════════════════════ -->

---

📖 **How to run this project: [RUNNING.md](RUNNING.md)**

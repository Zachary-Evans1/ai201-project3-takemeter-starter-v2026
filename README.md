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

### Community: r/pcgaming 

### Link to community: https://www.reddit.com/r/pcgaming/

### Candidate distinctions

1. News posts: The title is usually the headline of an article, and the post body contains a link to an article on another website.

2. Game trailers/ads: These usually contain an embedded video, and the title includes the game name and “Trailer.” Some announce that a game is available now and link to its store page.

3. Self-written posts: These contain mostly original text and cover a variety of topics. Some also include pictures.

4. Advertisements: These posts promote a company or product, sometimes unrelated to the subreddit’s main topic. Reddit marks some posts with an “Ad” label next to the username. Examples I noticed include posts from u/Netflix, u/Depop, and u/farmers insurance.

---

## What This Does

<!-- Your community, and what your classifier sorts posts into. Three or four
     sentences. -->

TakeMeter classifies Reddit posts from r/pcgaming into three categories: Gaming News, Game Trailers/Advertisements, and Self-Written. The goal of TakeMeter is to see how well a machine learning model can distinguish between these types of posts based on the examples I gave it to learn from.

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

**Where the posts came from:r/pcgaming on reddit**

**How I labelled them: I labeled all 200 posts myself without AI assistance, I sorted the posts by newest and did the first 200 posts that showed up from there.** <!-- Cold first? Pre-labelled with AI and corrected?
Say so plainly — the disclosure is required, not penalised. -->

**Counts per label:**

| Label | Count | Share |
|---|---|---|
| Gaming News | 71 | 35.5% |
| Game Trailers/Advertisements | 104 | 52% |
| Self-Written | 25 | 12.5% |
| **Total** | 200 | 100% |

**Three hard cases**

<!-- Any post that made you pause: what it was, which two labels it could have
     been, and what you chose. These are worth more than the easy 190. -->

**1.**
> *The post:*
> I've spent two years making a Doom-meets-Hotline Miami horror shooter named "BLOODVILLE" while in college, and it drops in two weeks.

Hey everyone,

For the last two years I've been balancing college and developing BLOODVILLE, and it officially launches on October 22nd.

BLOODVILLE is a short first-person shooter where you play as Cane, a retired hitman dragged back into killing - and slowly losing his mind.

What to expect:

Satisfying Combat - Aggressive gunplay mixed with drop-kicks and crunchy melee.

Tonal Whiplash - For every action-packed mission, there's a tense atmospheric/horror segment you must go through in order to progress.

Original Soundtrack - A mix of heavy Nine Inch Nails-inspired combat tracks and slow ambient cuts, included for free with the game in digital format.

You can check out the full gameplay trailer & Steam page here: LINK

Happy to answer any questions!*
> *Could have been:*
> Game Trailers/Advertisements or Self-Written
> *I chose, Game Trailers/Advertisements because:*
> It's a post by a developer made to sell a game, with a link to the trailer and the steam page, so I felt like it fit more into Game Trailers/Advertisements. It reads like a store page.
**2.**
> *The post:*
>The Black Pool is on sale for $5 for a few more hours, coop shooter roguelike with Returnal-esque vibes
I had this game on my wishlist for a long time and bought it during this sale, wish I had got it sooner. I'm very impressed and enjoying it a lot so far. Returnal, Lovecraft, SCP, Risk of Rain 2 all come to mind.

Its a 4 player coop 3rd person roguelike where you get to pick from 9 elements for your abilities, with each one having I think 6 variations, light attack, heavy attack, support, dash, jump, AOE buff. The elements each provide status effect bonuses as well, like filling the earth status makes the next damaging attack dealt double. You also get synergy unlocks between them.

As roguelikes go, you get upgrades for the skills as you progress, which I've found diverse for what I've seen. Example, I took ice for my jump skill, which makes a platform under you (and for your teammates if you play coop, I'm solo). Then I got an upgrade that gave me 40% chance to refresh the "double jump" cooldown up to 4 times, so I could make a trail of ice platforms up to an optional area in a level for extra powerups. I got a sick chaos boomerang spell that got a stacking dmg buff if I caught it on the way back (it had a return targeting reticle to stand on).

It's very bright and full of neon color illuminating fog, each element has its own color. The soundtrack is dark synth with an 80s vibe like Stranger Things.

I don't have anyone to gush about the game to, so I'm doing it here. It's on sale for $5 for the next few hours and it'd be cool to see more joinable games in the matchmaking list.
> *Could have been:*
> Game Trailers/Advertisements or Self-Written
> *I chose, Self-Written because:*
> The main purpose is the poster's recommendation and experience with the game, rather than just announcing the game is now selling
**3.**
> *The post:*
> Planetside 2 devs fix months old crash bug after a user shows them a solution

Ever since the "Auraximas" update in December 2025 the game has been plagued by a bug dubbed by the community as "flash or crash": Some short time after logging into the game or changing continents the game would crash without any error code. Not every player was affected but there are a lot of reports about this.

A workaround was found by immediately spawning any vehicle (with the "Flash" quad bike being the cheapest) and sitting in there for 2-3 minutes (staying on the loadout/respawn screen apparently worked as well for some). (Playing on Linux instead of Windows would also prevent this - although there was a phase where this also happened to Linux players).

However this could be a problem for new players as they are required to go through a tutorial where they may not be fast enough to get to the point of spawning a vehicle.

While the devs released some patches where the bug was seemingly fixed, it would later get reintroduced. There were a lot of fingers pointed at a connection with the BattleEye anti-cheat system (maybe not the software itself but its implementation) but during an update in September it was noted that "at the moment, we do not see any evidence in our logs that the anti-cheat system is contributing to the current situation")

Which brings us to last week, where a user did some debugging and seemingly found the root cause of the crash and presented a possible solution.

The workaround is consistent with a timing race. Asset streaming, worker scheduling, graphics callbacks, and background exception traffic can all change the chance of an active dispatch overlapping the broken cleanup window.

BattlEye is NOT the reason for the crash. BUT disabling it changes exception traffic and timing, which can make the race less likely for some players. The broken cleanup code is still inside the client either way.

That's why one player crashes almost every login while another player rarely sees it.

Fast forward to October 15th, where a hotfix is released that - as of now - fixes the bug. However with no credit being given. The devs haven't gone into detail either except one discord post saying: "we've looked it over but are not going to reveal specifics about it due to the sensitivity of the subject, but I can say it was not the solution the person had hoped".

The same user who found it also compared the changes introduced with that new fix, concluding that:

Based on that, I think it is very likely that my report helped them locate or confirm the bug, since I showed the exact line of code and the exact address causing the crash, which has been fixed in this patch.

As said, they didn't copy my implementation. They fixed the same problem I reported in the way that worked with their own build and protection pipeline.

I guess this may be another case where players fix the game for the developers.
> *Could have been:*
> Gaming News or Self-Written
> *I chose, Gaming News because:*
> Although it was written on Reddit and doesn't link to an external article, its written like a news article and does reports about a crash bug being fixed, so I decided it fit best in Gaming News.
---

## The Training Run

<!-- Your starting model, your settings, and anything you changed and why. -->

**Device and Torch Version: CPU, 2.14.1+cpu**

**Base model: distilbert-base-uncased**

**Settings: 3 epochs, learning rate 2e-5, batch size 16, and maximum token length 128. Seed: 42** <!-- epochs, learning rate, batch size, seed -->

**Anything I changed from the defaults, and why: Nothing**

**Split sizes: 139 training / 31 validation / 30 test.**
Test split per-label counts:

Gaming News: 11

Game Trailers/Advertisements: 15

Self-Written: 4
<!-- train / val / test, and per-label counts in the test
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

- *What I asked for: I asked ChatGPT to help me understand what an F1 score was.*
- *What came back: It explained how the F1 score worked.*
- *What I changed: I made my second criteria based on the F1 score for each label.*

**Moment 2**

- *What I asked for: I asked ChatGPT for a way to label the posts easier than writing them into a csv file directly.*
- *What came back: It told me to use Microsoft Excel, as you can convert an Excel file to a comma-delimited CSV file.*
- *What I changed: I did all the labeling in Excel then converted it to a CSV file, and moved that file into the project folder.*

**Moment 3**

- *What I asked for: I asked Claude what posts I might have mislabeled in my labels.csv file after giving it my definitions.*
- *What came back: It gave me eight examples where it believes I mislabeled a post.*
- *What I changed: I didn't change anything because I decided on a different change instead.*

**Pre-labelling disclosure: I did not use the AI to label the posts. I labeled all 200 posts manually.**

<!-- ═══════════════════════ UNIT 6 — THE TEST ═══════════════════════

     Don't fill these in during unit 5.
     ═══════════════════════════════════════════════════════════════════ -->

---

## Baseline vs. Trained

<!-- Both models on the same posts. `python baseline.py --trained results.json`
     prints this table for you. -->

| Measure | Baseline | Trained | Difference |
|---|---|---|---|
| Overall accuracy | 0.633 | 0.500 | -0.133 |
| Macro F1 | 0.534 | 0.222 | -0.312 |
| F1 — `Game Trailers/Advertisements` | 0.769 | 0.667 | -0.103 |
| F1 — `Gaming News` | 0.167 | 0.000 | -0.167 |
| F1 — `Self-Written` | 0.667 | 0.000 | -0.667 |

**What I predicted before I looked: I predict that my trained model will do better on the `Gaming News` and `Game Trailers/Advertisements` labels, but be worse on the `Self-Written` label.**
<!-- Milestone 1 asks you to write this BEFORE seeing the trained numbers. A
     prediction made afterwards isn't one. -->

**What the gap actually means: The baseline performed better than my trained model on this test set in every measure. This suggests that the fine-tuning did not improve performance in this run.**
<!-- If the baseline matched your trained model, your fine-tuning added
     nothing — and that is a real finding, not a failure. Say it plainly. -->



---

## Run Log — Before


### Spread Table from the notebook.

| Measure | Seed 42 | Seed 7 | Seed 2024 | Spread |
|---|---|---|---|---|
| Overall accuracy | 0.500 | 0.533 | 0.500 | 0.033 |
| Macro F1 | 0.222 | 0.283 | 0.222 | 0.061 |
| F1 — `Gaming News` | 0.000 | 0.167 | 0.000 | 0.167 |
| F1 — `Game Trailers/Advertisements` | 0.667 | 0.682 | 0.667 | 0.015 |
| F1 — `Self-Written` | 0.000 | 0.000 | 0.000 | 0.000 |

Accuracy moved 0.033 across seeds. Stable enough to trust.

<!-- Five criteria across three seeds. The notebook's section 6 prints the
     spread table; the Target and Verdict columns are yours. -->

| Criterion | Target | Seed 42 | Seed 7 | Seed 2024 | Verdict |
|---|---|---|---|---|---|
| 1. Overall Accuracy of 0.65 | Accuracy >= 0.65 | 0.500 | 0.533 | 0.500 | MISS |
| 2. Minimum Per-label F1 of 0.55 | F1 Per Label >= 0.55 | Not all pass | Not all pass | Not all pass | MISS |
| 3. The maximum share of the dataset one label can share is 65% | 65% or Max of 130 posts per label | Max was 105 | - | - | MET |
| 4. Consistency across seeds | Accuracy spread ≤ 0.10 | 0.033 | 0.033 | 0.033 | MET |
| 5. No Duplicates in Dataset | No Duplicate Posts | PASS | - | - | MET |

*Criteria 3 and 5 are dataset checks, so their results do not change across seeds.*

### Confusion matrix

<!-- ⚠️ TYPED AS A MARKDOWN TABLE. The notebook prints one ready to paste.
     An image of a matrix earns nothing. -->

| true \ predicted | Gaming News | Game Trailers/Advertisements | Self-Written |
|---|---|---|---|
| **Gaming News** | 0 | 11 | 0 |
| **Game Trailers/Advertisements** | 0 | 15 | 0 |
| **Self-Written** | 0 | 4 | 0 |

**My biggest off-diagonal number, and what it means: My biggest off-diagonal number was 11. 11 actual Gaming News Posts were labeled as Game Trailers/Advertisements. It seems the model might only be predicting things as Game Trailers/Advertisements, at least for seed 42.**
<!-- Not "the model made mistakes" — WHICH boundary it didn't learn, and which
     direction. "7 real analysis posts were called hot_take and only 3 went the
     other way" is a direction, not just an error rate. -->



---

## Verdicts and Diagnoses

<!-- MET or MISSED against LAST UNIT's target. The target has to hold across
     all three seeds, not turn up sometimes. -->

| # | Criterion | Target | Verdict | How I decided |
|---|---|---|---|---|
| 1 | Overall Accuracy of 0.65 | Accuracy >= 0.65 | MISSED | None of the three overall accuracy through the seeds reached 0.65 so this is a miss. |
| 2 | Minimum Per-label F1 of 0.55 | F1 Per Label >= 0.55 | MISSED | For all three seeds, not all labels passed, so this one was a miss. |
| 3 | The maximum share of the dataset one label can share is 65% | 65% or Max of 130 posts per label | MET | The highest share one label had was 52% with 104 posts, so this criteria was met. |
| 4 | Consistency across seeds | Accuracy spread ≤ 0.10 | MET | The consistency across seeds was 0.033 which is less than 0.10, so this passed.|
| 5 | No Duplicates in Dataset | No Duplicate Posts | MET | There were no duplicate posts in the data set, so this one passed. |

**Diagnoses**
Criteria 1 - Overall accuracy:

The model reached only 0.500, 0.533, and 0.500, below the 0.65 target in every run. Some possible inconsistencies in labels.csv may make the categories harder for the model to learn. In my Milestone 3 test I found that while I got 83% agreement with the staff labels, I had trouble consistently applying the rules for the analysis label. I think I may have had that problem here. I also asked Claude to check for any labels I may have mislabeled, it came back with 8 examples. I believe this is a labeling issue from this finding, but it may not be the only problem.


Criteria 2 - Every Label's F1

Gaming News: F1 was 0.000, 0.167, and 0.000. Self-Written: F1 was 0.000 for all three seeds. The confusion matrix shows the model repeatedly predicting Game Trailers/Advertisements instead of Gaming News or Self-Written. For Self-Written, the amount of data may be too small, only 4 posts were in the training data and the posts only make up 12.5% of the dataset. For Gaming News, the label boundary may be too difficult, or I may have applied it wrong in a few cases. I believe the low F1 scores may be caused by both the small number of Self-Written examples and possible labeling issues with Gaming News.

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

**Agreement rate:** 25 / 30 = 83%

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
>I tracked sleep against session quality for eleven weeks. Under seven hours the next day's intervals were 6-8 seconds per mile slower, every time bar one. Small sample, one runner, but it's consistent enough that I've stopped scheduling hard days after late shifts.
> *Staff said / I said:*
> analysis / reaction
> *My call, and why:*
> I think the staff is right here, the author makes a conclusion based on actual measured evidence in the post, which makes it an analysis rather than a reaction.
> *Which pile: A*

**2.**
> *The post:*
> The club championship scoring changed in 2019 from top-6 to top-10. Since then our B team has finished above the A team twice. That's not depth improving, it's the scoring rewarding turnout.
> *Staff said / I said:*
> analysis / hot_take
> *My call, and why:*
> Looking at the rules, I am wrong here. From rule 1 this is analysis, facts are used to support the conclusion. I choose hot take because I didn't think the post provided enough evidence, but thats not what was being asked.
> *Which pile: A*

**3.**
> *The post:*
> Everyone blames the hill at 18 miles. I split the field into people who ran the first half under 1:45 and over, and the slowdown after 18 was almost identical for both groups. If the hill were the problem the fast starters would fall apart harder.
> *Staff said / I said:*
> analysis / hot_take
> *My call, and why:*
> I feel like I made the right call here, the author definitely goes into this one with their conclusion already reached from the first sentence. Also "almost identical" is not a checkable fact. I can't verify the actual closeness of the figures from the post alone. The only number given in the 1:45 which is a grouping choice, and not a result. 
> *Which pile: C*

**4.**
> *The post:*
> Carbon plates aren't the whole story. My times dropped 2% in the shoes and another 2% the following year in the same pair, when the only thing that changed was going from 35 to 50 miles a week.
> *Staff said / I said:*
> analysis / reaction
> *My call, and why:*
> I feel like the staff are right here. The post states that after using carbon plates one year their time dropped by 2%, and the next year it fell the same 2% after they trained on longer distances. This supports the authors claim that carbon plates are not the only way to improve your time. I feel like I could have argued hot take, but it's definitely not a reaction. I still chose analysis because the evidence given is load bearing to the authors argument.
> *Which pile: A*

**5.**
> *The post:*
> Three of us ran the same session on the same day, different shoes, within 10 seconds of each other over 5 miles. I'm not saying shoes do nothing, but whatever they do was smaller than the noise between three people.
> *Staff said / I said:*
> analysis / hot_take
> *My call, and why:*
> I think the staff are right and this is analysis again. The post has evidence and then a conclusion derived from that evidence, which makes me think it's analysis instead of hot take.
> *Which pile: A*

**What the pattern in my disagreements tells me: I did not read the rules about analysis as closely as I should have. I did not apply rule 1 consistently, I sometimes judged whether the evidence was strong enough to prove the author's conclusion instead of asking whether the author used the evidence to support that conclusion. Evidence can be debatable while still being load-bearing to an arguemtn.**



---

## The Improvement

**What I changed: I added 30 Self-Written posts to labels.csv myself.**

**Which diagnosis pointed at it: Criteria 2, the F1 for Self-Written was 0 for all three seeds.**

### Run Log — After

| Criterion | Target | Seed 42 | Seed 7 | Seed 2024 | Verdict |
|---|---|---|---|---|---|
| 1. Overall Accuracy of 0.65 | Accuracy >= 0.65 | 0.457 | 0.514  | 0.571 | MISS |
| 2. Minimum Per-label F1 of 0.55 | F1 Per Label >= 0.55 | Not all pass | Not all pass | Not all pass | MISS |
| 3. The maximum share of the dataset one label can share is 65% | 65% or Max of 150 posts per label | Max was 105 | - | - | MET |
| 4. Consistency across seeds | Accuracy spread ≤ 0.10 | 0.114 | 0.114 | 0.114 | MISSED |
| 5. No Duplicates in Dataset | No Duplicate Posts | PASS | - | - | MET |

**Did it help, and how do I know: It did help the F1 of the Self-written posts in 2 seeds, but it was still 0 for 1 seed meaning it didn't meet the target for criteria 2. Overall it made things worse though, 2/3 seeds overall accuracy went down, the spread went up and now Criteria 4 misses, and it made the F1 for Gaming news even worse. The Fix did not help.**

<!-- If it didn't, say so. Relabelling that didn't help is a genuinely
     interesting result and earns full credit. -->



---

## What's Still Broken

<!-- For each criterion still missed: what you'd do, and why you stopped. -->

Criterion 1 - Accuracy: All three seeds are still below 0.65, scoring 0.457, 0.514, and 0.571. I would next review the labels for consistency and inspect examples where the model predicted the wrong category. I stopped because I had already made my one planned improvement for Milestone 5 and did not want to make another change without enough time to rerun and evaluate it across all three seeds.
Criterion 2 — Per-label F1: not every label reached 0.55. Gaming News had an F1 score of 0 for all three seeds, and Self-Written still had an F1 score of 0 for seed 42. I would investigate why Gaming News posts are being classified as Game Trailers/Advertisements. Also, I would check whether I applied label boundaries consistently. I stopped after the single improvement required for Milestone 5 rather than changing the labels or training setup again.
Criterion 4 — Consistency: the accuracy spread increased to 0.114, above the 0.10 limit. I would investigate why the model's performance varies so much between seeds. I stopped after completing the three-seed run for my chosen improvement; further investigation would require another experiment.


**The gap between what I meant my labels to capture and what the model
learned:**

My Confusion matrix shows that the model had difficulty distinguishing between the three categories. For Seed 42 it predicts Game Trailers/Advertisements for every test post, in both runs. This suggests my model learned to favor that category instead of learning the distinctions I intended between my three categories.
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

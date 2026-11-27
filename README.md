# Hoosier Diamond Directory

Indiana youth baseball directory — tournaments, batting cages, gear guides
(gloves, bats, training tools), first-season help, and Player Pool links.
Live at https://hoosier-diamond-directory.vercel.app (Vercel, free Hobby,
team coach-eric, project `hoosier-diamond-directory`).

## Structure (split Nov 27, 2026 — one real page per guide, for Google)

- `index.html` — home: search, page tiles, hero
- `tournaments.html` — Indiana Youth Baseball Tournaments (22 listings, age filter)
- `tournaments-10u.html` — Indiana 10U Tournaments 2027 (28 listings)
- `tournaments-12u.html` — Indiana 12U Tournaments 2027 (30 listings)
- `cages.html` — Batting Cages & Training in Indiana (11 listings, type filter)
- `cages-indianapolis.html` — Batting Cages Near Indianapolis (9 facilities)
- `cages-fort-wayne.html` — Batting Cages Near Fort Wayne (6 facilities)
- `bats.html` — Best Youth Bats by Age · `bat-sizing.html` — Bat Sizing Guide
- `gloves.html` — Best Gloves (size by age & position)
- `best-bat-10u.html` — Best Bat for 10U · `best-glove-10u.html` — Best Glove for 10U
- `training-tools.html` — Training Tools (tees, training bats, nets)
- `cleats.html` — Cleats & First-Season Starter Kit · `first-season.html`
- `bat-rules.html` — USSSA vs USA · `questions.html` — 12 Team Questions
- `player-pool.html` — Player Pool (player-pool.net) · `costs.html` — True Cost
- `how.html` — How It Works (outreach approval queue) · `privacy.html` · `disclosure.html`
- `sitemap.xml` + `robots.txt`

Each page is standalone HTML sharing one `<style>` block, with its own
`<title>`, meta description, canonical URL and H1, a static nav, and the
Vercel Analytics snippet. JS-rendered lists (tournaments, cages, bats,
gloves, kit, outreach queue) keep only the script chunk they need.
The builder that produced the split lives in `/tmp/split_build.py`
(source of truth: the original single-page file at the `314480f` commit).

## Adding a page

1. Add the section HTML (same `.page` section style, one H2 as the title).
2. Add an entry to the builder's `PAGES` list (title + meta description),
   rebuild with `python3 /tmp/split_build.py`, and check it renders.
3. Push to `main` — Vercel auto-deploys. Add the URL to `sitemap.xml`
   (the builder does this automatically from the PAGES list).

## Money

Product links are plain retailer links for now — no affiliate IDs yet.
Amazon Associates first, then Dick's via CJ (see
`~/workspace/hoosier-diamond-affiliate-prep.md`). Contact:
hoosierdiamonddirector@gmail.com. Facebook:
https://www.facebook.com/profile.php?id=61597191561908

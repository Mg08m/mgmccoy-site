# MG McCoy author site

Static site, no build step, no scripts, no third-party requests. Same approach as `lcmgproductions-site`.
Intended host: GitHub Pages (new public repo, `main`, root), custom domain to be bought (plan D2).

## Pages
- `/` author home, four book cards, readers-list form
- `/kept-ground/` the Kept Ground landing page (added 21 Oct 2026, branch `kept-ground-page`): headline, five-minute audiobook sample, readers-list form, AI-narration disclosure, Amazon ebook button; audiobook and paperback buttons wait for their store URLs
- `/scribe-2106/` the Scribe landing page: headline, free Chapter One form, AI-narration disclosure, store buttons below the fold
- `/scribe-2106/check-your-inbox/` form success page (set as the EmailOctopus form redirect)
- `/bound-water/` series page, reading order, Kept Fire waiting-list form
- `/privacy/` privacy notice

## Email capture (decided 18 Oct 2026, "plan B")
EmailOctopus free plan allows ONE embedded form, so one form serves the whole site:
"MG McCoy: free chapter and new releases", id `f71cac38-cb0c-11f1-92c1-29ba55965d88`, tags `scribe-free-chapter`
and `mg-mccoy-readers`. It is embedded on `/`, `/scribe-2106/` and the Kept Fire card on `/bound-water/` as
EmailOctopus's script (`https://eomail5.com/form/<id>.js`). The script sets no cookies or browser storage; the privacy
page says so. The separate Kept Fire waiting list was dropped: readers-list members get the one release email.
Success behaviour is a message shown in the form ("Check your inbox..."); `/scribe-2106/check-your-inbox/` is kept for
when a redirect is preferred.

## Hosting (live from 18 Oct 2026)
- Repo `Mg08m/mgmccoy-site`, GitHub Pages from `main` root, custom domain `mgmccoy.co.uk` (CNAME file).
- Cloudflare DNS, all DNS only: A @ -> 185.199.108.153 / 109.153 / 110.153 / 111.153; CNAME www -> mg08m.github.io.
- Edit in the repo, push `main`; Pages rebuilds in under a minute.
- EmailOctopus: sender verified, double opt-in on, both Chapter One automations active (see
  `content-launch/audiobooks/books/scribe-2106/emails/README.md`).

## Still open (owner)
0. Kept Ground: supply the audiobook store URL (and paperback once live) for the buttons on `/kept-ground/`; decide whether the readers-list form gets a Kept Ground tag/automation (free plan: one form, 3 automations, 2 in use), and update the form lead text on that page to match. The home hero still reads "Four standalone worlds"; Kept Ground makes five.
1. Add the registered office line to the footers once filed.
2. Covers: `scribe-2106-cover-800.jpg` (v6 square), `the-bound-water-cover-600.jpg` (revised edition, portrait),
   `kept-fire-cover-600.jpg` (final square audiobook cover, 18 Oct 2026). The Ordered Stone still shows a text placeholder.
3. Point Linktree and every social bio at https://mgmccoy.co.uk/scribe-2106/ (or the home page).
4. Once HTTPS is enforced on Pages, swap the Linktree links in EmailOctopus emails 03-05 for the site.

## Local preview
From the content-launch folder: `.claude/launch.json` has an `author-site` entry (`python -m http.server 8766`).

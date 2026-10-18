# MG McCoy author site

Static site, no build step, no scripts, no third-party requests. Same approach as `lcmgproductions-site`.
Intended host: GitHub Pages (new public repo, `main`, root), custom domain to be bought (plan D2).

## Pages
- `/` author home, four book cards, readers-list form
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

## Before go-live (owner)
1. Replace every `AUTHOR_DOMAIN` with the real domain (`grep -rl AUTHOR_DOMAIN .`).
2. In EmailOctopus, click the sender-verification link sent to hello@lcmgproductions.com, then switch on double opt-in
   (Contacts > Consent & customisation > Double opt-in; the email text is already filled in).
3. Upload Chapter One to a private path (or BookFunnel) and build the automation on tag `scribe-free-chapter`
   from `content-launch/audiobooks/books/scribe-2106/emails/`.
4. Add the registered office line to the footers once filed.
5. Covers: `assets/scribe-2106-cover-800.jpg` is the v6 square cover. `kept-fire-cover-600.jpg` is a DRAFT.
   The Bound Water and The Ordered Stone have no cover file here yet; the cards show a text placeholder.

## Local preview
From the content-launch folder: `.claude/launch.json` has an `author-site` entry (`python -m http.server 8766`).

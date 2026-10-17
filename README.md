# MG McCoy author site

Static site, no build step, no scripts, no third-party requests. Same approach as `lcmgproductions-site`.
Intended host: GitHub Pages (new public repo, `main`, root), custom domain to be bought (plan D2).

## Pages
- `/` author home, four book cards, readers-list form
- `/scribe-2106/` the Scribe landing page: headline, free Chapter One form, AI-narration disclosure, store buttons below the fold
- `/scribe-2106/check-your-inbox/` form success page (set as the EmailOctopus form redirect)
- `/bound-water/` series page, reading order, Kept Fire waiting-list form
- `/privacy/` privacy notice

## Before go-live (owner)
1. Replace every `AUTHOR_DOMAIN` with the real domain (`grep -rl AUTHOR_DOMAIN .`).
2. Replace `EMAILOCTOPUS_READERS_FORM_ACTION_URL` and the `field_0` name with the values from EmailOctopus
   > list "MG McCoy readers" > Forms > "HTML form". Use tags `scribe-free-chapter` and `kept-fire-waitlist`
   on the two book forms, or create one form per tag.
3. Set the Scribe form's success redirect to `/scribe-2106/check-your-inbox/`.
4. Upload Chapter One to a private path (or BookFunnel) and put that link in the day-0 automation email.
5. Add the registered office line to the footers once filed.
6. Covers: `assets/scribe-2106-cover-800.jpg` is the v6 square cover. `kept-fire-cover-600.jpg` is a DRAFT.
   The Bound Water and The Ordered Stone have no cover file here yet; the cards show a text placeholder.

## Local preview
From the content-launch folder: `.claude/launch.json` has an `author-site` entry (`python -m http.server 8766`).

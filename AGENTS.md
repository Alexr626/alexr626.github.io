# AGENTS.md: rules for agents working on this site

This is the personal academic website of Alexander (Alex) Romanus, served by GitHub Pages
at <https://alexr626.github.io> from the `main` branch. Its link goes into applications
that can't be edited after submission, so the site is where new work keeps appearing.
Two things matter most: every claim is accurate and credits co-authors correctly, and
routine updates touch one data file, not layout code.

**Read first, if it exists:** `source-materials/WEBSITE_TASK.md`, the full original brief.
It is local only (gitignored) because it holds private rules and context that must never
be published. Where it is more specific than this file, it wins, except where Alex
decided otherwise later (below). Never commit it, quote it, or copy its private details
into any committed file or commit message.

## Alex's decisions since the brief

- Nov 25, 2026: no per-paper contribution notes ("no one I've seen has done that on
  their personal websites"). The brief's draft notes are dropped.
- Nov 25, 2026: the contact email is set in `_data/profile.yml`, split into user and
  domain. Never write it out as one address anywhere in the repo.
- Nov 25, 2026: the current Nokia role started in Sep 2026. Every other experience entry
  was an internship or co-op; they are listed under an "Internships and co-ops"
  subheading (`group` in `_data/experience.yml`).
- Nov 25, 2026: Alex prefers blue and cool colours, with "a little pizzazz" over a plain
  page. The palette is cobalt and teal on a cool white, navy in dark mode; keep accents
  subtle.

This repo is public. Everything committed, including this file and the commit history,
is public.

## Truthfulness and sourcing

- Never invent content: no made-up awards, talks, affiliations, metrics, collaborators,
  quotes or links. Where something is missing, put a visible `[[TODO: ...]]` placeholder
  (any value containing `[[` renders highlighted) and list it at the end of the session.
- Sources, in priority order: what Alex says in chat; the full brief; the files in
  `source-materials/` (resume, research overview, paper PDFs).
- If sources conflict, don't pick one silently. Ask, or leave a `[[CONFIRM: ...]]`.
- Titles, author lists and arXiv IDs come exactly from the arXiv abstract pages or PDFs,
  never from memory. Alex's name is bolded automatically in author lists.
- Use specific, modest language: no hype ("groundbreaking", "first-ever",
  "state-of-the-art", "passionate about"), no buzzword stacks, no emojis.

## Research framing

- Primary direction: interpretability of representation learning in multimodal
  foundation models, currently vision-language models (VLMs): how they represent and
  combine visual and textual information, and using causal methods (causal tracing,
  activation patching, activation steering) to make them safer and more reliable.
- Don't describe all of Alex's work as mechanistic interpretability. Only the
  causal-tracing paper is. CausaLM is interpretability in the broader sense; FuzzingRL is
  VLM robustness evaluation, not interpretability.
- World models and JEPA-style representation learning are a longer-term interest, never
  experience.
- The full brief has further framing rules (what to keep low-key, what not to state).

## Publication status

- Each paper shows as "arXiv preprint, YEAR" with arXiv and PDF links. The status is the
  `venue` field in `_data/publications.yml`; change it only when a paper is accepted.
- Never name a venue a paper is under review at, on the site or anywhere in this repo.
  Major venues' anonymity policies forbid listing a submission on a public website, and
  the penalty can fall on every co-author.

## Privacy: never in the site or the repo

This covers page text, HTML comments, alt text, metadata, data-file comments and commit
messages.
- Phone number, home city or street address.
- GPA, unless Alex asks for it.
- PhD application details: schools, advisors contacted, recommenders, fellowship plans,
  outcomes, statements of purpose.
- Unpublished work: no results, numbers, figures or internal product names beyond the
  public resume. Some unpublished projects must not be mentioned at all; the full brief
  lists them.
- Email only obfuscated (`user [at] domain [dot] tld`), never a plain `mailto:`.
- No analytics, trackers, cookie banners or third-party embeds unless Alex asks.
- No secrets, tokens or `.env` files.

## Update workflow

Content lives in `_data/profile.yml`, `_data/publications.yml`, `_data/news.yml`,
`_data/experience.yml`, `_includes/intro.md` and `assets/cv/Alexander_Romanus_CV.pdf`.
When Alex asks for an update, edit the data file only, build, check the page, and
summarize what changed. Keep `README.md`'s "How to update the site" current.

The introduction is Alex's own copy: he line-edits it. Don't rephrase it into generic
language; if something must change, keep the technical specificity.

## Technical constraints

- Jekyll built natively by GitHub Pages: no GitHub Actions, only allow-listed plugins
  (`jekyll-seo-tag`, `jekyll-sitemap`), `theme: null`.
- Small custom theme: Liquid templates and one SCSS file. No JavaScript frameworks; the
  site currently has no JavaScript at all.
- If Alex asks for the al-folio look, confirm before switching: it needs an Actions
  deploy and is heavier to maintain.
- Design: one serif system font stack, ~70ch measure, one accent colour, light and dark
  via `prefers-color-scheme`, responsive down to 375px, WCAG AA contrast, visible focus,
  nothing conveyed by colour alone, explicit image width and height, Lighthouse 95+.

## Before pushing

Ask before pushing, creating repositories, changing GitHub settings, or publishing
unconfirmed copy. If `git push` is blocked, use the `gh api` push helper from Alex's
Cursor rules.

Checklist:
- Builds locally with no warnings, and every page renders.
- Every link works (arXiv, PDFs, Scholar, LinkedIn, GitHub, CV).
- Every author list and arXiv ID matches arXiv.
- Nothing from the privacy list appears anywhere.
- No paper is described as under review at a named venue.
- Mobile (375px) and dark mode checked.
- `README.md` is current.

## Working with Alex

Direct, concise communication; precise corrections over hedging. Each session ends with
what changed, how to preview it, and the open `[[TODO]]` and `[[CONFIRM]]` items.

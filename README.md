# alexr626.github.io

Personal research website of Alexander Romanus, served at <https://alexr626.github.io>.
GitHub Pages builds it with Jekyll from the `main` branch: pushing to `main` deploys it,
with no other step.

## How to update the site

All content lives in data files. Layout code doesn't need to change for routine updates.

| To change | Edit |
|---|---|
| A publication | `_data/publications.yml` |
| News | `_data/news.yml` |
| Experience | `_data/experience.yml` |
| The introduction | `_includes/intro.md` |
| Name, position line, links, email, headshot, CV link | `_data/profile.yml` |

**Add a publication.** Add an entry to `_data/publications.yml` in the position it should
appear (the first entry is the lead one). Copy the title and the author list exactly from
the paper's arXiv abstract page; your name is bolded automatically. Set
`venue: arXiv preprint` and `year`, `arxiv` (the ID, in quotes) and `pdf`. `code`,
`project`, `thumbnail` and `summary` (one line on what the paper does) are optional.
For a submitted paper, add `status: Under review`, which shows after the venue. Never name
the venue it's submitted to: most venues forbid listing submissions on public websites.
When a paper is accepted, set its `venue` to the venue's name and year and delete `status`.

```yaml
- title: "Paper Title Exactly As On arXiv"
  authors:
    - First Author
    - Alexander Romanus
  venue: arXiv preprint
  status: Under review                 # optional, never a venue name
  year: 2027
  arxiv: "2701.01234"
  pdf: https://arxiv.org/pdf/2701.01234
  code: https://github.com/...        # optional
  summary: >-                          # optional, one line on what the paper does
    One line on the paper.
```

**Add a news item.** Add it to `_data/news.yml` in date order, newest first (usually
at the top), with the date as `"YYYY-MM"`
and one line of text (Markdown links are fine). The page shows the five newest; older ones
move under a "Show all news" expander automatically.

```yaml
- date: "2027-02"
  text: "New preprint on ... posted to [arXiv](https://arxiv.org/abs/2702.01234)."
```

**Add a position.** Add it to `_data/experience.yml` with `role`, `org`, `dates` and an
optional one-line `description`. Give internships and co-ops
`group: Internships and co-ops` so they're listed under that subheading.

**Swap the CV.** Replace `assets/cv/Alexander_Romanus_CV.pdf`, keeping the file name, and
make sure the PDF has no phone number. The first time, set
`cv: /assets/cv/Alexander_Romanus_CV.pdf` in `_data/profile.yml`.

**Placeholders.** Any value containing `[[`, such as `[[TODO: ...]]` or
`[[CONFIRM: ...]]`, is shown highlighted on the page. Search the repo for `[[` to find
what is still open.

## Preview locally

The `Gemfile` uses the `github-pages` gem, so a local build matches the live one.

```bash
bundle install
bundle exec jekyll serve      # http://localhost:4000
```

On Windows, run these in WSL (Ubuntu). To keep the gems out of the repo, prefix both
commands with `BUNDLE_PATH=~/.gems/alexr626-site`. Behind a TLS-inspecting proxy,
`bundle install` needs `SSL_CERT_FILE` set to a CA bundle that includes the proxy's root
certificate.

## Layout

```
_config.yml            site settings, plugins (jekyll-seo-tag, jekyll-sitemap), excluded files
_data/                 profile, publications, news, experience
_includes/intro.md     the introduction (Markdown)
_includes/*.html       header, email, publication and news entries, JSON-LD Person data
_layouts/default.html  page shell and footer ("Last updated" is the build date)
assets/css/main.scss   the only stylesheet (light and dark colours at the top)
assets/img/            headshot (400x400, metadata stripped), favicon.svg
assets/cv/             public CV PDF
```

`source-materials/` (resume, drafts, paper PDFs) stays local and is gitignored.

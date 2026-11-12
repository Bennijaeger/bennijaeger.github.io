# Website update from the CV (branch `cv-update`)

This branch replaces the al-folio demo content with content taken from the CV source
(`Application_Jaeger_revised.tex`) and from the INSPIRE-HEP author record 1272234.
Nothing has been pushed.

## What changed

| Area | Change |
|:--|:--|
| Navigation | about · publications · research · teaching · cv. Blog, repositories, people, submenus and the Portuguese (pt-br) version removed. |
| `_config.yml` | Name `Jäger`; keywords; Open Graph/schema.org meta on; GitHub `Bennijaeger`; new field `inspirehep_id`; demo giscus/disqus/medium ids removed; author highlighting for Jäger/Jaeger/Jager; `max_author_limit: 5`; Altmetric and thumbnails off; JSON-resume source removed (it overrode `cv.yml`). |
| `_i18n/en.yml` | Subtitle, office address, contact note, footer, page descriptions, research-card and news titles. |
| About (`_i18n/en/_pages/about.md`) | Biography, current topics, computing allocations, teaching. Selected papers and news are shown below it. |
| News (`_news/`) | 7 items (2025–2026). |
| Publications | `papers.bib` regenerated from INSPIRE: 105 entries (26 journal, 78 proceedings, 1 thesis), grouped by the CV's categories via a custom `category` field. 5 highlighted papers marked `selected`. Full author lists restored where INSPIRE truncates to "and others". |
| `_layouts/bib.liquid` | Added DOI and INSPIRE buttons; journal volume and pages shown. |
| `_includes/social.liquid` | Added INSPIRE-HEP icon. |
| Research (`_projects/1–7`, `/research/`) | Six research topics from the research statement plus interdisciplinary work and Quantum Kate. Each page lists its references. |
| Teaching (`_pages/teaching.md`) | Course table, supervision counts, programme roles, pedagogical training, short teaching philosophy. |
| CV (`_data/en/cv.yml`) | Positions, education, interests, funding, computing allocations (core-hours only), service, interdisciplinary activities, training, 39 conferences and 26 seminars. No PDF link. |

| `_includes/projects.liquid` | Research-card titles keep their capitalisation (template forced lower case, e.g. "qcd"). |
| `_pages/teaching.md` | Tables carry Bootstrap `table table-sm` classes. |
| `README.md` | Replaced the template README with a short description of where each part of the content lives; removed the template screenshots in `assets/img/readme_preview`. |
| `papers.bib` details | Your name normalised to `J{\"a}ger` in all author fields (INSPIRE has Jager/Jaeger variants); lower-case particles braced (`{von Hippel}`, `{de Forcrand}`, `{de Boni}`) so they are not dropped; LaTeX math in 11 titles replaced by HTML/Unicode (e.g. U(1)<sub>A</sub>, (g−2)<sub>μ</sub>) because the theme's LaTeX filter strips `$…$`. |
| `_config.yml` excludes | `docker-compose-slim.yml`, `reports/`, `CHANGES.md` no longer copied into the built site. |

Deliberately **not** published: private address and phone number, date of birth (was in the old `cv.yml`), the application letter, the promotion plan, the five-year plan, and the notional DKK values of the computing allocations.

## Please verify

1. **INSPIRE misattribution.** INSPIRE lists `Jager:2022hzc` (*Precision measurements of Higgs boson production in decays to W bosons*, a thesis by a different person) under your profile. It is excluded from `papers.bib`; you may want to request a correction on INSPIRE.
2. **New paper not yet in the CV.** `DArcy:2026ndz`, *Thermal modifications of the B-meson spectrum*, arXiv:2609.14440 (13 Sep 2026), is included as a journal-category preprint.
3. **Computing allocations since 2023.** The CV table has eight allocations starting in 2023 or later, five of them as PI; the CV text says "five of the seven". The website avoids the ratio. Total from the table: 1816.9 M CPU + 3.32 M GPU core-hours (matches "1.82 billion").
4. **Supervision numbers.** The itemised table gives 1 PhD student supervised + 2 co-supervised, 16 Master's, 11 Bachelor's, 28 first-year students, 1 + 1 postdocs. The CV summary on page 2 says "four PhD students … ten Bachelor's". The website uses the table.
5. **News dates.** Three items have only a year in the CV and were given placeholder dates: Degree Responsible Mathematics–Economics (2026-01-01), EuroHPC 2026–2027 allocation (2026-01-01), teaching-award nomination (2025-06-01). Please correct in `_news/announcement_5–7.md`.
6. **Spring 2014 PhD course** (*Introduction to Lattice Field Theory*) has no institution in the CV; assumed Swansea.
7. **Institute name.** The website uses "Danish Institute for Advanced Study" (the CV writes "Studies").
8. **EuroPLEx amount.** Shown as "Co-PI, ≈30.6 million DKK" as in the CV. If that is the network total rather than the SDU share, consider stating so.
9. **Contribution statements** on the research pages are taken from the CV section marked `% VERIFY` in the source.
10. Typos corrected on the website only (also present in the CV source): "Behavious" → "Behaviour", "Stravanger" → "Stavanger", "Dublin, IR" → "Dublin, IE".

## Local build check

The branch was built locally with Jekyll 4.4.1 / Ruby 3.2 (`bundle exec jekyll build`): no errors; only Sass deprecation warnings from the theme. The rendered publication page contains 26 journal, 78 proceedings and 1 other entry; all 35 citation keys on the research pages resolve. Note that building on macOS needs a UTF-8 locale (`export LANG=en_US.UTF-8`); GitHub Actions uses UTF-8 by default.

## Publishing

```bash
cd ~/Projects/Webpage/bennijaeger.github.io
git push -u origin cv-update          # review on GitHub, then
git checkout main && git merge cv-update && git push
```

Deployment: `deploy.yml` runs after the "Check for broken links" workflow succeeds (push to `main` touching assets/md/html files), or manually via *Actions → Deploy site → Run workflow*. GitHub Pages must serve from the `gh-pages` branch (*Settings → Pages*).

## Updating later

- Publications: re-export from INSPIRE (`https://inspirehep.net/api/literature?q=authors.record.$ref:1272234&size=250&format=bibtex`), then add `category`, `selected`, `abbr` fields as in the current file.
- News: add a file to `_news/` with a `news.titles.newsN` key in `_i18n/en.yml`.
- CV: edit `_data/en/cv.yml` directly.

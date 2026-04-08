# HCLH Workshop Website

This repository contains the official website for the **High-Accuracy Computing on Low-Precision Hardware (HCLH)** workshop. The site is hosted via GitHub Pages and serves as the primary source of information for authors, speakers, and attendees.

## Site structure

- **Single home page:** All public sections live on `index.md`, assembled from `_includes/home-sections.html` and `_data/*.yml`.
- **Top navigation:** Defined in `_data/nav.yml` (in-page anchors plus external **Venue** link). **Archive** is not included.
- **Legacy URLs:** Old paths (`call-for-papers.md`, `program.md`, etc.) remain as tiny **redirect** pages to the matching section on the home page.

## Content workflow (what to edit)

| You want to change… | Edit… |
|---------------------|--------|
| Workshop name, tagline, banner, overview paragraphs, optional **overview logo** beside Workshop Overview | `_data/workshop.yml` (`overview_logo.file` / `overview_logo.alt`) |
| Schedule, program blurb | `_data/program.yml` |
| CfP (intro, topics, submission text, proceedings note, portal URL/label) | `_data/submission.yml` |
| Important dates | `_data/dates.yml` |
| Organizers, program committee, featured speakers | `_data/people.yml` |
| People to contact (shown at end of Call for papers) | `_data/contact.yml` — list under `contacts` with `name` and `email` per person; optional legacy `email` if `contacts` is empty |
| Accepted papers (optional; not shown on the site until you add a section again) | `_data/accepted-papers.yml` |
| Nav labels or Venue URL | `_data/nav.yml` |

To change section **order** or add a new anchored section, update both `_includes/home-sections.html` and `_data/nav.yml` (and any redirect stubs if you rename anchors).

For local preview, set `url` and `baseurl` in `_config.yml` according to the [Jekyll docs](https://jekyllrb.com/docs/configuration/options/) for your environment.

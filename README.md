# HCLH Workshop Website

This repository contains the official website for the **High-Accuracy Computing on Low-Precision Hardware (HCLH)** workshop. The site is hosted via GitHub Pages and serves as the primary source of information for authors, speakers, and attendees.

## Site structure

- **Single home page:** All public sections live on `index.md`, assembled from `_includes/home-sections.html` and `_data/*.yml`.
- **Top navigation:** Defined in `_data/nav.yml` (in-page anchors plus external **Venue** link). **Archive** is not included.
- **Legacy URLs:** Old paths (`call-for-papers.md`, `program.md`, etc.) remain as tiny **redirect** pages to the matching section on the home page.

## Content workflow (what to edit)

| You want to change… | Edit… |
|---------------------|--------|
| Workshop name, tagline, status, SC venue/date, banner, default overview paragraphs, topics, outcomes | `_data/workshop.yml` — optional opening copy: `overview_extra` (list of paragraphs) |
| Schedule, program blurb | `_data/program.yml` |
| CfP instructions, topics, submission portal/template/limits | `_data/submission.yml` |
| Important dates | `_data/dates.yml` |
| Organizers, program committee, featured speakers | `_data/people.yml` |
| Contact email, sponsorship email, update bullets | `_data/contact.yml` |
| Accepted papers list | `_data/accepted-papers.yml` |
| Nav labels or Venue URL | `_data/nav.yml` |

To change section **order** or add a new anchored section, update both `_includes/home-sections.html` and `_data/nav.yml` (and any redirect stubs if you rename anchors).

For local preview, set `url` and `baseurl` in `_config.yml` according to the [Jekyll docs](https://jekyllrb.com/docs/configuration/options/) for your environment.

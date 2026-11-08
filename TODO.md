# Final updates checklist (HCLH workshop site)

Live site: https://hclh-sc.github.io/ (status as of 2026-11-03). Edit the referenced files and push to `main`; the site rebuilds automatically.

---

## Status

- [x] Schedule table matches the SC26 program (`sess147`), and the date, time and room are in the schedule intro (`_data/program.yml`, `_data/accepted-papers.yml`).
- [x] Invited speakers and panelists are listed with photos and bios (`_data/people.yml`).
- [x] Submission portal, author instructions and proceedings note are set (`_data/submission.yml`).
- [x] Important dates are set, including the extended deadlines (`_data/dates.yml`).
- [x] Contacts are set (`_data/contact.yml`).
- [ ] Confirm that `workshop_submission_label` matches the official SC workshop listing (see section 2).

---

## 1. Invited speakers and panelists

**File:** `_data/people.yml`

**What to update:** Add one entry per person under `invited_speakers` (invited talks) or `panelists` (panel). Each list has its own section on the page (*Invited speakers*, *Panelists*); an empty list shows "TBD". Each entry can include:

| Field           | Required | Notes |
|-----------------|----------|--------|
| `name`          | Yes      | Full name |
| `affiliation`   | Yes      | Institution or company |
| `title`         | No       | Optional short line (talk title or position); shown after an em dash |
| `photo`         | No       | Path to a square headshot (200×200 works well), e.g. `/assets/images/speakers/jane-doe.jpg`; without one, an initials placeholder is shown |
| `bio`           | No       | List of plain-text paragraphs; without one, no bio is shown |
| `tbd`           | No       | `true` marks a placeholder for a speaker not yet announced: a dashed "TBD" box replaces the photo. Remove it when filling in the real person |

**Example:**

```yaml
invited_speakers:
  - name: Jane Doe
    affiliation: Example University
    title: Invited talk — Mixed precision at scale
panelists:
  - name: John Smith
    affiliation: National Lab (NL)
```

**Where it appears:** the *Invited speakers* and *Panelists* sections, one after the other (`_includes/home-sections.html` and `_includes/speaker-cards.html` read these lists). Photos live in `assets/images/speakers/`.

**Schedule (same page):** Rows in **`_data/program.yml`** can have a `session:` label plus an optional `details:` list (shown on lines under the label). Rows with `paper: N` pull the title and authors from entry N of **`_data/accepted-papers.yml`**.

---

## 2. Submission details

**File:** `_data/submission.yml`

| Item | Field(s) | State |
|------|-----------|-------|
| **Submission URL** | `portal_url`, `portal_label` | Set. Shown as a link that opens in a new tab. |
| **Workshop name in submission sentence** | `workshop_submission_label` | **Still to confirm** against the official SC workshop listing. |
| **Proceedings sentence** | `proceedings_note` | Set. Adjust if the official wording changes. |
| **Author instructions** | `submission_guidelines` | Set (page limit, IEEE template, double-blind). The IEEE template link is written inline in this text. |
| **Placeholder text** | `portal_link_placeholder` | Only shown when `portal_url` is empty, so it is not shown now. |
| **Reference metadata** | `template_url`, `page_limit`, `review_model` | Not shown anywhere on the page. If you change the template or limits, update `submission_guidelines`, which is what visitors see. |

**Links:** External links open in a new tab. In YAML text, write them as `<a href="https://…" target="_blank" rel="noopener noreferrer">text</a>`, because plain Markdown links `[text](url)` open in the same tab.

**Important dates:** **`_data/dates.yml`** has one row per deadline with a `label` and `date`, plus an optional `extended_date`. When `extended_date` is set, the original date is shown struck through, followed by the extended one. Add more rows for extra milestones.

**Contacts:** **`_data/contact.yml`**. Update `contacts` (names and emails) if organizer contact points change.

---

## After you edit

1. Commit and push to the branch GitHub Pages builds (`main`).  
2. Wait for the Pages build to finish (usually a minute or two), then hard-refresh the live site.  
3. If the build fails, check the **Actions** tab on the repo; YAML syntax errors (quotes, colons in unquoted strings) are the usual cause.

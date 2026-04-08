# Final updates checklist (HCLH workshop site)

Use this list when workshop details are finalized. Edit the referenced files and push to GitHub; the site will rebuild automatically.

---

## 1. Invited speakers and panelists

**File:** `_data/people.yml`

**What to update:** Under `featured_speakers`, replace the empty list with one entry per speaker or panelist. Each entry can include:

| Field           | Required | Notes |
|-----------------|----------|--------|
| `name`          | Yes      | Full name |
| `affiliation`   | Yes      | Institution or company |
| `title`         | No       | Optional short line (talk title or role); shown after an em dash |

**Example:**

```yaml
featured_speakers:
  - name: Jane Doe
    affiliation: Example University
    title: Invited talk — Mixed precision at scale
  - name: John Smith
    affiliation: National Lab (NL)
```

**Where it appears:** **Workshop Schedule** section → subsection *Invited speakers / panelists* (`_includes/home-sections.html` reads this list).

**Optional (same section):** To adjust session titles or times in the table, edit **`_data/program.yml`** (`intro`, `schedule` rows).

---

## 2. Submission details

**File:** `_data/submission.yml`

| Item | Field(s) | What to do when final |
|------|-----------|------------------------|
| **Official submission URL** | `portal_url` | Set to the SC submissions site URL (e.g. Supercomputing workshop submission page). |
| **Link label** | `portal_label` | Short text for the hyperlink (e.g. `SC submission site`). If empty, the URL text is used. |
| **Placeholder (before URL exists)** | `portal_link_placeholder` | Optional: shorten or remove text; once `portal_url` is set, this is not shown. |
| **Workshop name in submission sentence** | `workshop_submission_label` | Confirm wording matches the official SC workshop listing (e.g. `SC26 Workshop: HCLH'26: …`). |
| **Proceedings sentence** | `proceedings_note` | Adjust if the official proceedings wording changes. |
| **Author instructions** | `submission_guidelines` | Update page limits, template (**IEEE** vs **ACM** or other), and blind/double-blind policy to match the final CfP. |
| **Optional template link** | `template_url` | If you want a visible “template” link in Call for papers, set the URL; leave empty to hide that bullet. |
| **Reference metadata** | `page_limit`, `review_model` | Keep in sync with `submission_guidelines` (used if you surface them elsewhere; template block label in `home-sections` still says “ACM” when `template_url` is set—edit `_includes/home-sections.html` line ~84 if the publisher name changes). |

**Related — important dates (deadlines on the page):** **`_data/dates.yml`**

Replace `TBA` with real dates for:

- Submission deadline  
- Notification of acceptance  
- Camera-ready deadline  

(Add more rows if you need extra milestones.)

**Related — contacts:** **`_data/contact.yml`**

Update `contacts` (names/emails) if organizer contact points change.

---

## After you edit

1. Commit and push to the branch GitHub Pages builds (usually `main`).  
2. Wait for the Pages build to finish, then hard-refresh the live site.  
3. If the build fails, check the **Actions** tab on the repo; YAML syntax errors (quotes, colons in unquoted strings) are the usual cause.

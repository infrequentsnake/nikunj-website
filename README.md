# nikunjkhurana.com

Personal site for **Nikunj Khurana**, Actuarial Studies student.

Plain HTML, CSS and a little vanilla JavaScript. No build step, no dependencies,
no `node_modules`. Edit a file, refresh the browser, done.

**Changing the wording yourself? See [EDITING.md](EDITING.md).** No installs
needed, it all happens in the browser.

## Run it locally

```bash
python3 -m http.server 4321 --directory ~/nikunj-website
```

Then open <http://localhost:4321>.

## Structure

```
nikunj-website/
├── index.html          Home: hero, facts, about, project cards, charity teaser, contact
├── projects.html       The project write-ups (self-directed, not coursework)
├── charity.html        Charity projects, coming soon
├── netlify.toml        Deploy config (no build; clean URLs; cache headers)
└── assets/
    ├── css/style.css   All styling. Design tokens live at the very top.
    ├── js/main.js      Mobile nav, sticky header, scroll reveals
    ├── img/favicon.svg
    └── downloads/      Files offered for download, e.g. the Excel calculator
```

## Editing

**Design tokens.** Colours, fonts and spacing are CSS variables in the `:root`
block at the top of `assets/css/style.css`. Change one value there and it updates
across every page.

| Token | Value | Used for |
| --- | --- | --- |
| `--cream` | `#FAF7F5` | Page background |
| `--ink` | `#06080F` | Headings and primary text |
| `--sage` | `#566455` | Muted and meta text |
| `--olive` | `#728557` | Primary accent, buttons, links |
| `--rust` | `#B83A2D` | Secondary accent, used sparingly |

**Projects.** Each write-up in `projects.html` is one `<article class="project-entry">`
block with a matching summary card in `index.html`. The two are linked by anchor
(`#buying-house-calculator`, `#frontier-lab`, ...), so keep them in sync when renaming.

**Adding another project.** Copy an existing `project-entry` block, give it a new
`id`, and copy a `project-card` in `index.html` pointing at that `id`. Don't write
the number of projects into any sentence, since the list keeps growing.

## Still to fill in

- [x] Real project titles, categories, years and write-ups
- [x] Contact email, phone and LinkedIn
- [x] Portrait photo at `assets/img/portrait.png` (transparent background, so the
      cream card colour shows through). Replace that file to change the photo.

## Deploying

Hosted on Netlify at <https://nikunj-khurana.netlify.app>, deployed from
<https://github.com/infrequentsnake/nikunj-website>.

Pushing to `main` triggers a rebuild. There is no build step, so Netlify just
publishes the folder. Ask Claude in this chat to make a change and it will commit
and push for you.

# nikunjkhurana.com

Personal site for **Nikunj Khurana**, Actuarial Studies student.

Plain HTML, CSS and a little vanilla JavaScript. No build step, no dependencies,
no `node_modules`. Edit a file, refresh the browser, done.

## Run it locally

```bash
python3 -m http.server 4321 --directory ~/nikunj-website
```

Then open <http://localhost:4321>.

## Structure

```
nikunj-website/
├── index.html          Home: hero, facts, about, project cards, charity teaser, contact
├── projects.html       The three project write-ups (self-directed, not coursework)
├── charity.html        Charity projects, coming soon
├── netlify.toml        Deploy config (no build; clean URLs; cache headers)
└── assets/
    ├── css/style.css   All styling. Design tokens live at the very top.
    ├── js/main.js      Mobile nav, sticky header, scroll reveals
    └── img/favicon.svg
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
(`#frontier-lab`, `#nasdaq-backtest`, `#cgt-calculator`), so keep them in sync when renaming.

**Adding a fourth project.** Copy an existing `project-entry` block, give it a new
`id`, and copy a `project-card` in `index.html` pointing at that `id`.

## Still to fill in

- [x] Real project titles, categories, years and write-ups
- [x] Contact email, phone and LinkedIn
- [ ] Portrait photo. Drop it at `assets/img/portrait.jpg` and swap the
      `.portrait__placeholder` block in `index.html` for an `<img>`

## Deploying

Hosted on Netlify at <https://nikunj-khurana.netlify.app>, deployed from
<https://github.com/infrequentsnake/nikunj-website>.

Pushing to `main` triggers a rebuild. There is no build step, so Netlify just
publishes the folder. Ask Claude in this chat to make a change and it will commit
and push for you.

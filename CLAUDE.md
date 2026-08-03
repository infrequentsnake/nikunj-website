# Nikunj Khurana — personal site

Static personal site for Nikunj Khurana, an Actuarial Studies student at UNSW Sydney.

## Ground rules

- **No build step and no dependencies.** There is no Node on this machine. Plain
  HTML, CSS and vanilla JS only — do not introduce a framework, bundler or
  `package.json` without being asked.
- Run locally with `python3 -m http.server 4321 --directory .` (a `.claude/launch.json`
  is already set up, so `preview_start` with the name `nikunj-site` works).
- Styling is centralised: design tokens live in the `:root` block at the top of
  `assets/css/style.css`. Prefer changing a token over adding one-off rules.

## Design language

Warm, light and editorial — inspired by derivenotes.com.

| Token | Value | Role |
| --- | --- | --- |
| `--cream` | `#FAF7F5` | Page background |
| `--ink` | `#06080F` | Headings, primary text |
| `--sage` | `#566455` | Muted / meta text |
| `--olive` | `#728557` | Primary accent |
| `--rust` | `#B83A2D` | Secondary accent, used sparingly |

Playfair Display for headings, Inter for body, JetBrains Mono for labels, course
codes and tags. The faint graph-paper texture is deliberately confined to the
`.gridpaper` sections (hero and charity page) so it never sits behind body copy.

## Structure

- `index.html` — hero, facts strip, about, project cards, charity teaser, contact
- `projects.html` — three project write-ups
- `charity.html` — coming soon

Projects are **self-directed work Nikunj does outside university**, not coursework.
Keep the wording clear of "academic", "course", "term" and "assignment" — project
metadata is Category / Year / Tools / Status.
- Project cards in `index.html` link to anchors in `projects.html`
  (`#project-one`, `#project-two`, `#project-three`). Keep them in sync.

## Deploying

Netlify site **`nikunj-khurana`**, site ID `1e4aa53a-6e08-43c9-915b-422c25b0aa95`,
live at https://nikunj-khurana.netlify.app

Deploy with the Netlify MCP `deploy-site` operation using that site ID. **Only ever
deploy with this folder as the working directory** — the deploy tool publishes the
working directory, and this project previously sat inside the user's home folder
where a deploy would have exposed personal files.

## Outstanding

The three projects are still placeholders (`Project One`, `CATEGORY`) awaiting real
content. Contact details are real as of 3 August 2026. Every page carries a
`<meta name="robots" content="noindex, nofollow">` while the project copy is
placeholder — remove those three tags once the real write-ups land.

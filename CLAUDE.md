# Nikunj Khurana, personal site

Static personal site for Nikunj Khurana, an Actuarial Studies student at UNSW Sydney.

## Ground rules

- **No build step and no dependencies.** There is no Node on this machine. Plain
  HTML, CSS and vanilla JS only. Do not introduce a framework, bundler or
  `package.json` without being asked.
- Run locally with `python3 -m http.server 4321 --directory .` (a `.claude/launch.json`
  is already set up, so `preview_start` with the name `nikunj-site` works).
- Styling is centralised: design tokens live in the `:root` block at the top of
  `assets/css/style.css`. Prefer changing a token over adding one-off rules.

## Design language

Warm, light and editorial, inspired by derivenotes.com.

| Token | Value | Role |
| --- | --- | --- |
| `--cream` | `#FAF7F5` | Page background |
| `--ink` | `#06080F` | Headings, primary text |
| `--sage` | `#566455` | Muted / meta text |
| `--olive` | `#728557` | Primary accent |
| `--rust` | `#B83A2D` | Secondary accent, used sparingly |

Playfair Display for headings, Inter for body, JetBrains Mono for labels,
category chips and tags. The faint graph-paper texture is deliberately confined to the
`.gridpaper` sections (hero and charity page) so it never sits behind body copy.

## Structure

- `index.html`: hero, facts strip, about, project cards, charity teaser, contact
- `projects.html`: three project write-ups
- `charity.html`: coming soon

Projects are **self-directed work Nikunj does outside university**, not coursework.
Keep the wording clear of "academic", "course", "term" and "assignment". Project
metadata is Category / Year / Built with / Status.
- Project cards in `index.html` link to anchors in `projects.html`
  (`#frontier-lab`, `#nasdaq-backtest`, `#cgt-calculator`). Keep them in sync.

The three projects, all his own work:
1. **Frontier Lab** (portfoliomaximiser.netlify.app): React portfolio optimiser,
   six assets in AUD, 2000 to 2025.
2. **Nasdaq options backtest**: Python, DCA vs selling puts vs covered calls,
   Mar 1999 to Jul 2026. No live app.
3. **CGT calculator** (newbudget.netlify.app): React, models the proposed 2027
   indexation rules against the old 50% discount.

## Deploying

Netlify site **`nikunj-khurana`**, site ID `1e4aa53a-6e08-43c9-915b-422c25b0aa95`,
live at https://nikunj-khurana.netlify.app

**Deploy by pushing to GitHub** with `git push origin main`, and Netlify rebuilds
automatically. The repo is `git@github.com:infrequentsnake/nikunj-website.git`
(GitHub user `infrequentsnake`), authenticated with the existing SSH key at
`~/.ssh/id_ed25519`. No credentials to enter.

Do **not** use the Netlify MCP `deploy-site` operation: it returns an `npx` command,
and there is no Node on this machine. It also publishes the *working directory*, so
running it from the user's home folder would expose personal files.

## House style

- **No em dashes anywhere**, including code comments. Use commas, colons, full
  stops or parentheses. This is an explicit standing instruction from the user.
- **"UNSW" appears at most twice on the whole site.** It currently sits in the hero
  eyebrow and the facts strip on `index.html`, and nowhere else. Don't reintroduce
  it into titles, meta tags or the nav.
- Prose follows the `humaniser` skill: vary sentence length, use contractions,
  prefer concrete numbers over adjectives, and keep the honest caveats in.

## Outstanding

Project copy and contact details are real as of 3 August 2026. A portrait is still
missing (`assets/img/portrait.jpg`). Every page still carries
`<meta name="robots" content="noindex, nofollow">`; remove all three tags when the
user confirms they want the site indexed by search engines.

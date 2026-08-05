# Editing the website yourself

You don't need Claude, a code editor, or anything installed. You edit the text in
your browser, and the live site updates about ten seconds later.

## The quickest way: github.dev

1. Go to <https://github.com/infrequentsnake/nikunj-website>
2. Press the **`.`** key (full stop). A full editor opens in your browser.
3. Click a file on the left: `index.html`, `projects.html` or `charity.html`.
4. Change the words you want.
5. Click the **Source Control** icon on the far left (the little branching arrows).
6. Type a short note about what you changed, then click **Commit & Push**.

That's it. Netlify rebuilds on its own. Wait about ten seconds, then reload
<https://nikunj-khurana.netlify.app>.

## The even simpler way, for a one line change

1. Open the file on GitHub, for example
   <https://github.com/infrequentsnake/nikunj-website/blob/main/index.html>
2. Click the **pencil icon** at the top right.
3. Edit, then click **Commit changes** at the top right.

## The one rule

Change only the words **between** a `>` and a `<`.

```html
<h1>Nikunj Khurana</h1>
    ^^^^^^^^^^^^^^ safe to change
```

Leave alone anything inside the angle brackets, like `class="hero__lead"` or
`href="projects.html"`. That's the layout, not the words. If you delete a `<` or a
`>` by accident, the page will look broken. See "If it breaks" below, it's fixable
in one click.

Every part you're likely to want is marked in the files with a comment starting
`EDIT:`, so you can search for `EDIT:` to jump between them.

## Where things live

| What you want to change | File | Search for |
| --- | --- | --- |
| Your name, tagline, opening paragraph | `index.html` | `EDIT: the hero` |
| The four fact boxes | `index.html` | `EDIT: the four fact boxes` |
| Skill pills (React, Python, R...) | `index.html` | `EDIT: the skill pills` |
| The About paragraphs | `index.html` | `EDIT: the About heading` |
| Project summary cards | `index.html` | `EDIT: card for` |
| Full project write-ups | `projects.html` | `EDIT: Project` |
| Email, phone, LinkedIn | `index.html` | `EDIT: your contact details` |
| The charity page | `charity.html` | `EDIT:` |

## Two small things

**Apostrophes.** The text uses the curly `’` rather than the straight `'`. If you
type a straight one it'll still work and almost nobody will notice, so don't worry
about it.

**Contact details appear twice.** In the contact list, the link and the visible
words are separate, so change both:

```html
<a href="mailto:nikunj.khurana5@gmail.com">
  <span class="contact-key">Email</span>
  <span>nikunj.khurana5@gmail.com</span>
</a>
```

## Seeing it before you publish

Run this on the Mac and open <http://localhost:4321>:

```bash
python3 -m http.server 4321 --directory ~/nikunj-website
```

Edit the files in `~/nikunj-website`, refresh the browser, and you'll see changes
instantly without publishing anything.

## If it breaks

Nothing is ever lost, because every save is a separate version.

1. Go to <https://github.com/infrequentsnake/nikunj-website/commits/main>
2. Find the change that caused it.
3. Open it and click **Revert**.

Or just ask Claude in the chat to undo the last change, which is usually faster.

## What you can't break

The design, the fonts, the colours and the layout all live in
`assets/css/style.css`. You never need to open it to change words. If you want the
look changed rather than the wording, that's the file, and it's easier to ask.

# How to update your website

This is your reference for adding posts, updating pages, and managing your
site without needing to use a terminal. The whole site is managed through
GitHub.com in a web browser. Bookmark this page; you can re-read any
section whenever you need it.

If you only read one thing, read **[Part 1: How the site is laid out](#part-1-how-the-site-is-laid-out)**
and **[Part 4: Writing a new blog post, step by step](#part-4-writing-a-new-blog-post-step-by-step)**.
Everything else you can come back to.

---

## Table of contents

- [Part 1: How the site is laid out](#part-1-how-the-site-is-laid-out)
- [Part 2: The tools you'll use](#part-2-the-tools-youll-use)
- [Part 3: How a change goes from edit to live website](#part-3-how-a-change-goes-from-edit-to-live-website)
- [Part 4: Writing a new blog post, step by step](#part-4-writing-a-new-blog-post-step-by-step)
- [Part 5: Adding a new project card](#part-5-adding-a-new-project-card)
- [Part 6: Adding pictures](#part-6-adding-pictures)
- [Part 7: Markdown cheatsheet](#part-7-markdown-cheatsheet)
- [Part 8: Front-matter cheatsheet (the `+++` block)](#part-8-front-matter-cheatsheet-the--block)
- [Part 9: Common edits you'll want to make](#part-9-common-edits-youll-want-to-make)
- [Part 10: When something breaks](#part-10-when-something-breaks)
- [Part 11: Going further (optional)](#part-11-going-further-optional)
- [Glossary](#glossary)

---

## Part 1: How the site is laid out

Your website is built from plain text files in this repository. Every page,
every post, every project card is just a file. To change what's on the
site, you change a file.

Here are the folders that matter:

```
content/
  about.md                  ← your About page
  publications.md           ← your Publications page
  speaking.md               ← your Speaking page
  posts/
    creative-resistance-zine-launch.md   ← a blog post
    (new posts go here)
  projects/
    c2pan.md                ← a project card
    craft-consulting.md
    (new project cards go here)

static/
  images/                   ← all your pictures
    posts/                  ← pictures for blog posts
    projects/               ← pictures for project cards
  cv/
    Betsy_Craft_CV.pdf      ← your downloadable CV

config.toml                 ← site-wide settings:
                              your name, the menu, social links,
                              the contact form email, etc.
```

Three rules to remember:

1. **Every page and post is a file inside `content/`.**
2. **Every picture is a file inside `static/images/`.**
3. **Site-wide settings, and home page content, live in `config.toml`.**

That's it. There's no database, no admin panel, no login screen to manage.
Just files in folders.

---

## Part 2: The tools you'll use

You only really need two things, both free, both browser-based to start:

### 1. A GitHub.com account (you already have one)

This is where the website's files live. You'll be editing right in the
browser at github.com.

### 2. (Optional but very nice) Markdown Live Preview

When you're writing in markdown, it's helpful to see what it'll look like.
GitHub previews markdown automatically when you edit a `.md` file, but
some people like the dedicated preview at <https://markdownlivepreview.com>
where you can paste in your draft and see it formatted in real time.

That's it for daily use. **No terminal, no software to install.** As you
get more comfortable you can add nicer tools (see [Part 11](#part-11-going-further-optional)),
but you don't need any of that to start.

---

## Part 3: How a change goes from edit to live website

It helps to know what happens behind the scenes when you save a change.

1. **You edit a file on github.com** (you'll see how in Part 4).
2. **You click "Commit changes"** at the bottom of the edit screen. This
   saves your change to the repository with a short note about what you
   did.
3. **GitHub automatically rebuilds your website.** A robot called GitHub
   Actions takes your text files and turns them into the real HTML site,
   then publishes it to `creativeresistanceco.com`. This usually takes 30 seconds
   to 2 minutes.
4. **The live site updates.** You may need to refresh the page in your
   browser (Cmd-R on a Mac, Ctrl-R on Windows) to see the new version.

You can watch the rebuild happen in the **Actions** tab of your
repository on GitHub. A green check mark means it worked; a red X means
something went wrong (see [Part 10](#part-10-when-something-breaks)).

> **The big idea:** *every save is a commit, every commit triggers a
> rebuild, every rebuild updates the live site.* You don't have to
> "publish" anything separately.

---

## Part 4: Writing a new blog post, step by step

Let's say you want to write a post about an event.

### Step 1 — Open the repository on github.com

Go to your repository in a browser. You'll see all the folders listed
in Part 1.

### Step 2 — Navigate to `content/posts/`

Click `content`, then click `posts`. You'll see the existing post files.

### Step 3 — Create a new file

Click the **Add file** button (top right), then choose **Create new file**.

### Step 4 — Name the file

Give it a name like:

```
new-upcoming-event.md
```

Use only **lowercase letters, numbers, and dashes** — no spaces, no
capital letters, no apostrophes. The `.md` at the end is required (it
tells the site this is a markdown file). This name becomes part of the
URL on your site, so make it short and descriptive.

### Step 5 — Paste in this template

Copy and paste the following into the editor:

```
+++
date = "2026-05-15"
title = "Creative Resistance: arts-based activism and drug policy in Colorado"
description = "Join us June 25 in Denver for an evening with Heather Edney celebrating the launch of 8:32, a drug user-led Harm Reduction zine."
[taxonomies]
tags = ["harm reduction", "speaking"]
[extra]
image = '/images/posts/creative-resistance-zine.jpg'
+++

Write your post here.

You can use **bold**, *italics*, and [links](https://example.com).

## A subheading

A paragraph under the subheading. Leave a blank line between paragraphs
so they render correctly.

- A bulleted list
- Another item
- A third item

> A blockquote, for pulling a quote out.

A regular paragraph at the bottom to close it out.
```

### Step 6 — Fill in your real content

- Change the `date` to today (format: `YYYY-MM-DD`).
- Change the `title` to your real title.
- Write a one-sentence `description` — this is what shows up as the
  preview text on the blog index page.
- Update the `tags` to whatever fits (you can put as many or as few as
  you want; they create filterable tag pages automatically).
- For `image`, either point at an existing image or upload a new one
  first (see [Part 6](#part-6-adding-pictures)) and use that path.
- Replace the body text with your actual post.

### Step 7 — Commit your changes

Scroll to the bottom of the page. You'll see a **Commit changes** box.

- The first line is the commit message — write something short like
  `Add post: event announcement for zine launch`.
- Leave the radio button on "Commit directly to the `main` branch."
- Click the green **Commit changes** button.

### Step 8 — Wait, then check the site

Go to your live site at `creativeresistanceco.com/posts/`. Wait 30 seconds to a
couple of minutes, then refresh. Your new post should appear.

If it doesn't appear after a few minutes, check the **Actions** tab of
your repo for an error. See [Part 10](#part-10-when-something-breaks).

---

## Part 5: Adding a new project card

The process is identical to a blog post, except:

1. You put the file in `content/projects/` instead of `content/posts/`.
2. You can copy and adapt this template instead:

```
+++
date = "2026-05-16"
draft = false
title = "Project name"
description = "One-line description shown on the project card."
[taxonomies]
tags = ["harm reduction", "Colorado", "project"]
[extra]
image = '/images/projects/project-name.jpg'
+++

The body of the project page goes here. Describe the project, who's
involved, your role, and link out to related resources.

[Link out to a related website →](https://example.com)

### A subsection if you want one

More body text.
```

### How dates are used on project cards

The `date` controls the order projects appear on the Projects page and
on the homepage — newer dates show up first. If you want a specific
project to be at the top, give it the most recent date.

### Marking a project as not-yet-public

If you want to draft a project page without publishing it yet, set
`draft = true` in the front-matter. It won't appear on the site until
you change it to `draft = false`.

---

## Part 6: Adding pictures

Pictures live in the `static/images/` folder. The path you reference in
your post or project file always starts with `/images/...`. That's
because everything inside `static/` shows up at the root of the website.

So a file saved at `static/images/posts/creative-resistance-zine.jpg` is
linked in your markdown as:

```
/images/posts/creative-resistance-zine.jpg
```

### Step-by-step: uploading a new image

1. **Pick the right folder.**
   - For blog post images: `static/images/posts/`
   - For project card images: `static/images/projects/`
   - For other images (an About page photo, a hero image): `static/images/`

2. **Name the image file** with only lowercase letters, numbers, and
   dashes, plus the file extension. Good: `creative-resistance-zine.jpg`.
   Bad: `IMG_4837 (1).JPG`.

3. **Resize and compress before uploading** (important — saves your site's
   load time):
   - Aim for about **1600 pixels wide maximum** for hero/full-width
     images, and **800 pixels wide** for card thumbnails.
   - Use JPEG (`.jpg`) for photos and PNG (`.png`) for graphics with
     flat colors or transparency.
   - Free in-browser tool: <https://squoosh.app>. Open your image, set
     the width on the right side, and download the smaller version.

4. **Upload it to GitHub.**
   - On github.com, navigate to the target folder (e.g.,
     `static/images/posts/`).
   - Click **Add file** → **Upload files**.
   - Drag your image into the upload area.
   - At the bottom, write a short commit message like
     `Add image for Creative Resistance zine event` and click
     **Commit changes**.

5. **Reference it in your post or project.**

   - In the front-matter (this is the card/header image):
     ```
     image = '/images/posts/creative-resistance-zine.jpg'
     ```
   - In the body of the post (inline image with caption-style alt text):
     ```
     ![Full color picture of event flyer for "Creative Resistance: Arts-Based Activism and Drug Policy in Colorado"](/images/posts/creative-resistance-zine.jpg)
     ```

The `alt` text in square brackets is what screen readers read aloud and
what shows up if the image fails to load. Always write something
meaningful — never leave it empty.

---

## Part 7: Markdown cheatsheet

Markdown is the simple text formatting language you'll use for posts and
pages. Here's everything you'll regularly need:

```
# Big heading (only use one per page — usually you don't need this
   because the title from the front-matter is the page's main heading)

## Section heading

### Smaller subheading

A normal paragraph. Leave a blank line between paragraphs.

**Bold text** and *italic text* and ***bold italic***.

A link to [the Colorado Drug Policy Coalition](https://www.codpc.org).

A bulleted list:

- First item
- Second item
- Third item

A numbered list:

1. First
2. Second
3. Third

> A blockquote for pulling out a powerful quote.

An inline image:

![Description of the image for accessibility](/images/posts/my-image.jpg)

A horizontal rule:

---
```

A few small but real gotchas:

- **Blank lines matter.** Two lines of text right on top of each other
  with no blank line between them will render as one paragraph.
- **Lists need a blank line before them.** If you put `- item` directly
  under a paragraph, sometimes it doesn't render as a list. Put a blank
  line in between.
- **Don't paste from Word or Google Docs directly.** Word documents
  bring in invisible formatting characters that can confuse the site.
  Always paste through a plain text editor first (on a Mac, you can use
  TextEdit in "Plain Text" mode), or type your post directly into the
  GitHub editor.

---

## Part 8: Front-matter cheatsheet (the `+++` block)

The `+++ ... +++` block at the top of every page and post is called
**front-matter**. It's metadata that tells the site how to display your
content. Order doesn't matter, but spelling and formatting do.

### Required fields

| Field | What it is | Example |
|---|---|---|
| `title` | The headline of the page | `title = "My Post Title"` |
| `date` | When it was published, format `YYYY-MM-DD` | `date = "2026-05-16"` |

### Common optional fields

| Field | What it is | Example |
|---|---|---|
| `description` | Preview text shown on the blog/project index | `description = "A short summary"` |
| `draft` | Hide from the site if `true` | `draft = false` |

### Tags

Tags go inside their own `[taxonomies]` block. You can have as many as
you want. Each unique tag automatically gets its own tag page.

```
[taxonomies]
tags = ["harm reduction", "Colorado", "speaking"]
```

### Extra (custom) fields

The `[extra]` block holds anything the template needs that isn't standard
Zola front-matter. The main one you'll use is `image`:

```
[extra]
image = '/images/posts/my-image.jpg'
```

### Common mistakes that break front-matter

- **Missing closing `+++`.** Every front-matter block has to open AND
  close with `+++` on its own line.
- **Forgetting quotes around strings.** Wrap titles and descriptions in
  double quotes: `title = "My Title"`, not `title = My Title`.
- **Wrong date format.** Always `YYYY-MM-DD` like `2026-05-16`, not
  `5/16/2026`.
- **Curly quotes from Word.** Word and Pages auto-replace `"straight
  quotes"` with `"curly quotes"`. The site will reject those. Use
  straight quotes only.

---

## Part 9: Common edits you'll want to make

### Change your bio on the About page

Edit `content/about.md`. The body of the page is inside the
`content_html = """ ... """` block — that's three double-quotes opening
and three closing. Edit the text between them.

### Add a new publication

Edit `content/publications.md`. Find the `<ol>` (ordered list) for
peer-reviewed articles and add a new `<li>` entry following the same
format as the others. Don't forget the `</li>` closing tag.

### Add a new talk to the Speaking page

Edit `content/speaking.md` the same way — find the right section,
copy an existing `<li>` entry, and adapt it.

### Update your social media links

Edit `config.toml`. Find the `social_icons = [ ... ]` block (around line
40-something) and change the URLs.

To add an additional icon, copy an existing line. The `icon` value has to
match a known icon name (the site uses Ionicons logos). Common ones that
work: `LinkedIn`, `Instagram`, `Twitter`, `Github`, `Facebook`,
`YouTube`, `RSS`.

### Change the contact form email

Edit `config.toml`. Find the line:

```
form_submission_email = "betsy.coloradodpc@gmail.com"
```

and replace the email.

### Update your CV

Drop the new PDF into `static/cv/` and name it exactly
`Betsy_Craft_CV.pdf` so all the existing "Download CV" links keep
working. (If you want to use a different filename, you'll need to also
update the links — they appear in `content/about.md`, `content/publications.md`,
`content/speaking.md`, and `config.toml`.)

To upload a new PDF on github.com:

1. Go to `static/cv/`.
2. Click **Add file** → **Upload files**.
3. Drag in the new PDF (named `Betsy_Craft_CV.pdf`).
4. Commit. This will overwrite the previous version.

---

## Part 10: When something breaks

### The site didn't update after I committed

1. Wait 2 minutes — builds usually take 30–60 seconds but sometimes
   longer.
2. Go to the **Actions** tab of your repo. The most recent build at the
   top will be running (yellow circle), succeeded (green check), or
   failed (red X).
3. If it's red, click on it to see the error message. The error usually
   names the file with the problem.

### Common reasons a build fails

- **Bad front-matter** — typically a missing closing `+++`, a missing
  quote, or a typo in `[taxonomies]` or `[extra]`.
- **Wrong date format** — use `YYYY-MM-DD`.
- **Curly quotes or weird characters from copy-pasting** — see Part 8.
- **An image you referenced doesn't exist** — this won't fail the build,
  but the image will appear broken on the page.

### "I made an edit and now I want to undo it"

You can always go back. Every commit is permanent history. To revert:

1. Find the commit you want to undo. On github.com, go to the **Commits**
   page (you can get there from the repo home page by clicking on the
   most recent commit message, then "View all commits").
2. Click the commit you want to undo.
3. In the top right, click the three-dot menu and choose **Revert**.
4. This creates a new commit that undoes the old one. Click
   **Commit changes**.

Or for a much simpler case — if you just made an edit you regret and
haven't committed yet — just close the browser tab without clicking
**Commit changes**. Nothing was saved.

### "I accidentally deleted a file"

Same idea — find the commit where you deleted it, and revert that
commit. The file will come back.

### When in doubt, ask

Don't be afraid to leave it in a half-broken state and ask for help.
The site keeping running depends on the `main` branch being valid, so
nothing you can do in a new commit is irreversible — every change has a
history and can be undone.

---

## Part 11: Going further (optional)

Once you're comfortable editing on github.com, here are nicer tools to
graduate to when you want. None of these require a terminal.

### GitHub Desktop — git without typing

<https://desktop.github.com> is GitHub's free desktop app. It lets you
"clone" the website to your computer, edit files in any editor, and
commit through buttons rather than command-line git. Useful if you want
to edit a bunch of files at once or work offline (on a flight, in a
coffee shop without wifi).

### Visual Studio Code — a nicer markdown editor

<https://code.visualstudio.com> is a free editor with a beautiful
side-by-side markdown preview. Open the folder GitHub Desktop downloaded,
and edit away.

A useful built-in shortcut: with a `.md` file open, press
**Cmd-K then V** (Mac) or **Ctrl-K then V** (Windows) to open the live
preview pane on the right.

### Running the site locally to preview (more advanced)

If you want to see what a draft post will look like on your site before
committing, you can install Zola (the program that builds the site) and
run it locally. This requires a one-time terminal command to install,
but after that it's just one command (`zola serve`) to start a local
preview at `http://127.0.0.1:1111`. There's a good install guide at
<https://www.getzola.org/documentation/getting-started/installation/>.

Don't worry about this until you actually feel limited by the github.com
editor.

### Learning markdown more deeply

<https://www.markdownguide.org/basic-syntax> is a good reference once
you outgrow the cheatsheet in Part 7.

### Learning git more deeply

<https://lab.github.com> and <https://learngitbranching.js.org> are both
free, interactive, and friendly. You don't need to learn git in depth to
maintain this site — but if you ever want to, those are great starting
points.

---

## Glossary

**Branch** — a parallel version of the repository. Your site uses one
called `main` (the source) and one called `gh-pages` (the built site).
You only ever need to touch `main`.

**Commit** — one saved change to the repository, with a short message
explaining what changed. Each commit is permanent history; you can
always look back at or revert to any past commit.

**Front-matter** — the `+++` block at the top of every content file.
It's metadata: title, date, tags, image, etc.

**Git** — the version control system that tracks every change to your
repository. You don't need to use git directly; GitHub.com hides it
behind buttons.

**GitHub** — the website that hosts your repository.

**GitHub Actions** — the robot that rebuilds and republishes your site
whenever you commit a change.

**GitHub Pages** — GitHub's free service for hosting a static website
from a repository. Yours points at `creativeresistanceco.com`.

**Markdown** — the simple plain-text formatting language you write
posts and pages in. See Part 7.

**Push** — copying commits from your computer up to GitHub. When you
edit on github.com directly, this happens automatically.

**Repository (or repo)** — the project folder, with all its files and
history.

**Static site** — a website made of plain HTML files (no database, no
server-side code). Cheap to host, fast to load, very hard to break.

**Zola** — the program that turns your markdown files in `content/` into
the actual HTML pages of your website. You don't need to install it —
GitHub Actions runs it automatically.

---

*Last updated: May 2026. If something in here is wrong or unclear,
edit this file (yes, you can edit your own guide!) and commit the fix.*

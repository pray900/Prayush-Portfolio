# Prayush Shrestha — Portfolio

A single-page developer portfolio with a terminal/matrix aesthetic, built as one self-contained HTML file and deployed to GitHub Pages.

**Live site:** https://pray900.github.io/Prayush-Portfolio/

## About

The site presents my background as a software engineer — Salesforce development, full-stack work, and data/ML projects — across seven sections, each named after a file or command to match the terminal theme:

| Section | Contents |
| --- | --- |
| `home()` | ASCII banner and intro inside a terminal window |
| `about.md` | Bio alongside a syntax-highlighted "developer profile" code block |
| `skills.json` | Six skill categories as tag grids |
| `experience.log` | Work history as a vertical timeline |
| `projects.repo` | Project cards with GitHub and live-demo links |
| `blogs.txt` | Links to my Medium articles |
| `contact.sh` | Email, LinkedIn, and location |

## Stack

- **HTML5 + CSS3** — no frameworks, no build step, no dependencies to install
- **CSS custom properties** for the dark palette (`--accent-green: #00ff88`, `--accent-blue: #00d4ff`)
- **JetBrains Mono** loaded from Google Fonts
- **GitHub Actions + GitHub Pages** for deployment

Everything — markup, styles, and content — lives in [index.html](index.html).

## Structure

```
.
├── .github/
│   └── workflows/
│       └── static.yml    # Deploys the repo root to GitHub Pages
├── index.html            # The entire site
└── README.md
```

## Running locally

Clone and open the file — there is nothing to build or install:

```bash
git clone https://github.com/pray900/Prayush-Portfolio.git
cd Prayush-Portfolio
start index.html          # Windows  (macOS: open index.html)
```

For a local server instead (useful for consistent relative paths):

```bash
python -m http.server 8000
# then visit http://localhost:8000
```

## Deployment

[`.github/workflows/static.yml`](.github/workflows/static.yml) publishes the repository root to GitHub Pages on every push to `main`, and can also be triggered manually from the **Actions** tab. Deployments are serialized via a `pages` concurrency group so an in-progress release is never cancelled.

To enable it on a fork: **Settings → Pages → Build and deployment → Source: GitHub Actions**.

## Editing the content

All content is plain markup in `index.html`, so updates are copy-and-paste edits:

- **New project** — duplicate a `<div class="project-card">` block in the `#projects` section and change the title, links, description, and `tech-tag` spans.
- **New blog post** — duplicate a `<div class="blog-card">` block in the `#blogs` section.
- **New role** — duplicate a `<div class="timeline-item">` block in the `#experience` section.
- **New skill group** — duplicate a `<div class="skill-category">` block in the `#skills` section.
- **Colors** — edit the `:root` custom properties near the top of the `<style>` block.

## Notes

The hero section includes a `<canvas id="matrix">` background and a `<span id="typing-output">` placeholder for a typing animation, but the page currently ships no JavaScript, so both render empty. Adding a small inline `<script>` would bring those two effects to life; the CSS for them is already in place.

## Contact

- **Email:** prayush900@gmail.com
- **LinkedIn:** [Prayush Bahadur Shrestha](https://www.linkedin.com/in/prayush-shrestha-syd/)
- **Medium:** [@prayush900](https://medium.com/@prayush900)
- **Location:** Sydney, Australia

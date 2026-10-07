# Sandeep Gadakari — Portfolio

A hand-drawn 3D portfolio you walk through: AI product management, from the
business case to the live app. Six rooms open off a corridor — **Demos**,
**Dashboards**, **Tableau**, **Code**, **AI Systems** and **The Study** — with 26
projects hung on the walls, seven of them live apps. Built as a single HTML
file: no build step, no framework, no bundler. three.js is the only dependency,
loaded from a CDN.

**Live:** <https://sandeep-gadakari-portfolio.vercel.app>

## What's in the building

- **The front** introduces you before anyone clicks: the name and project count
  on the fascia, one lit window per room (click a window to go straight in), a
  chalk board for what's new, and a mailbox that opens an email. The doors open
  as you walk up the path. After 7 pm on the visitor's clock the outside turns
  to night and each window glows in its room's colour (`?time=day` or
  `?time=night` overrides). `SETTING` in the script switches the Dubai street
  back to the original meadow; `BOARD` holds the chalk board's lines.
- **Posters** show the real apps and dashboards, redrawn in ink. The images are
  baked once into `art/` (about 400 KB for all thirteen).
- **Case-study spreads**: the eight flagship projects open into a two-page
  sketchbook — the problem, how it works, the decisions that mattered, the
  numbers, and what isn't done yet. Their content is the `CASES` block.
- **The Study** (Room 06): the path so far, the certificates, and the CV on the
  desk. Until `CV_URL` is set, the desk asks for the CV by email.
- **The guide** at the desk in the corridor (or **ASK**, top left) answers
  questions about the work from the project write-ups, in the browser: no API,
  no key, and nothing a visitor types leaves the page.
- **Blueprint mode**, a **floor plan** that shows where you are, and on phones
  rooms that frame **one poster at a time** — swipe or use the arrows.

## Running it locally

Serve the folder, so the dashboards and the ink posters load as they do live:

```bash
python -m http.server 8000
```

Opening `index.html` straight from disk also works, but browsers won't let a
`file://` page hand its own images to WebGL, so the posters fall back to their
drawn art, and the dashboards under `projects/` parse spreadsheets in-page
instead of in a background worker.

Without WebGL — or with *reduce motion* enabled — the site renders a full
accessible HTML gallery of the same content instead of the 3D walk.

## A note on the client work

Several dashboards here were delivered to a client during an internship. Every
one of them has been anonymised before publication: company and entity names,
employee names, org-chart cards and embedded logos are all replaced, and the
retail control tower opens on a **synthetic** sample dataset generated for this
repo. No real client data is included anywhere in this repository or its history.

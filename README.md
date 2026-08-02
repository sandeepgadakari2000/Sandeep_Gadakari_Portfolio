# Sandeep Gadakari — Portfolio

A hand-drawn 3D portfolio you walk through. Five rooms open off a corridor —
**Demos**, **Dashboards**, **Tableau**, **Code**, and **AI Systems** — with 22
projects hung on the walls. Built as a single self-contained HTML file: no build
step, no framework, no bundler. three.js is the only dependency, loaded from a CDN.

**Live:** <https://sandeep-gadakari-portfolio.vercel.app>

## Running it locally

Open `index.html` in a browser. That's it.

A few of the dashboards under `projects/` parse spreadsheets in a background
worker, which browsers restrict on `file://` origins. They fall back to parsing
in-page automatically, so double-clicking works — but if you want them running
exactly as deployed, serve the folder instead:

```bash
python -m http.server 8000
```

Without WebGL — or with *reduce motion* enabled — the site renders a full
accessible HTML gallery of the same content instead of the 3D walk.

## A note on the client work

Several dashboards here were delivered to a client during an internship. Every
one of them has been anonymised before publication: company and entity names,
employee names, org-chart cards and embedded logos are all replaced, and the
retail control tower opens on a **synthetic** sample dataset generated for this
repo. No real client data is included anywhere in this repository or its history.

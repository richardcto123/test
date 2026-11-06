# Working in this project

This is an Astro site edited visually with [sitereal](https://sitereal.app).
The pages, components and stylesheets are ordinary files; `site.sitereal`
holds what the visual editor needs (page trees, design system, settings), and
the site never reads it.

- **Prefer sitereal's MCP tools when they are connected** (`sitereal_*`):
  a write through them updates the visual editor and every file that depends
  on it, and the user sees it on the canvas.
- **Editing a file directly is fine.** Pages, components (styles and script
  included), layouts, popups, HTML snippets, the stylesheets sitereal writes,
  the variables in `framework.css` and a collection's `src/data/<slug>.json`
  are read back into the visual editor, and a file you formatted keeps its
  formatting when the editor changes it. **A new `.astro` file under
  `src/pages/` becomes a page**: one shaped like the others is an ordinary
  page, anything else stays its own file, with nothing put around it. A
  collection stored as entry files keeps each entry as `src/entries/<slug>/*.md`
  (or `.json`): write a new one to add an entry. A line sitereal derives
  from a setting — a site-wide head prop, a frontmatter line it generates —
  is not read back into the project, but your file keeps it. sitereal
  never writes over a file edited outside it: a change from the editor is
  merged into your edit, and where both changed one line yours stands.
  Deleting a page's file deletes the page. Say which files you edited.
- **Do not put rules into `src/styles/generated/framework.css`** (the design
  system's output): a rule written there is moved into `global.css`. Put CSS
  in your own stylesheet instead; the design system is changed in the app.
- Never edit `site.sitereal` by hand.

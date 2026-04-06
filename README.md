# Bento Roadmap

A local-first, single-file product roadmap tool. No backend, no build step, no npm. Just open `index.html` in a browser and start planning.

![Bento Roadmap screenshot](example.html)

## Features

- **Bento grid layout** — tiles snap to a 6-column grid with 7 size presets (1×1, 2×1, 3×1, 4×1, 6×1, 2×2, 3×2)
- **Drag & drop** — reorder tiles within and across sprints with animated FLIP transitions
- **Inline editing** — click any title, description, tag, or sprint name to edit in place
- **Status cycling** — click the status badge to cycle through Backlog → In progress → Done → Blocked
- **Tile modal** — click a card to open a full detail view with notes field
- **Sprint management** — add, rename, reorder, and delete sprints
- **Persistent** — data lives in `localStorage`; nothing leaves your browser
- **Import / Export** — save and load your roadmap as a plain JSON file
- **Responsive** — adapts from desktop down to mobile
- **WCAG AA contrast** — all text meets 4.5:1 minimum contrast ratio

## Usage

1. Download or clone this repo
2. Open `index.html` in any modern browser
3. Start editing — your changes save automatically

No server, no installation, no account required.

## Keyboard & interaction reference

| Action | How |
|--------|-----|
| Edit title / description | Click the text |
| Cycle status | Click the status badge (bottom-left of card) |
| Edit tag | Click the tag label |
| Resize tile | Hover card → click ⤡ (bottom-right) → pick a size |
| Delete tile | Hover card → click × (top-right) |
| Add tile | Click any ghost `+` cell |
| Move tile | Drag and drop |
| Add sprint | Click `+ sprint` in the header |
| Delete sprint | Hover sprint name → click × |
| Open detail | Click anywhere on a card (not a control) |
| Export | Click `export` in the header → downloads `roadmap.json` |
| Import | Click `import` in the header → pick a `.json` file |

## Data format

Roadmaps are stored as JSON (in `localStorage` and exported files):

```json
{
  "title": "My Roadmap",
  "sprints": [
    {
      "id": "s1",
      "name": "Sprint 1",
      "date": "Apr 6 – Apr 19",
      "tiles": [
        {
          "id": "t1",
          "title": "Feature name",
          "description": "Short description",
          "notes": "",
          "status": "backlog",
          "tag": "frontend",
          "cols": 2,
          "rows": 1
        }
      ]
    }
  ]
}
```

**Status values:** `Backlog` · `In progress` · `Done` · `Blocked`

## Contributing

Pull requests are welcome. The entire app is in `index.html` — HTML structure at the bottom, CSS in `<style>`, JS in `<script>`. No bundler, no dependencies beyond two Google Fonts.

Ideas for contributions:
- Dark mode
- Tile colors / labels
- Keyboard shortcuts
- Multiple roadmap tabs
- Offline-first via Service Worker

## License

MIT License

Copyright (c) 2026

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

# ECO.SYSTEM.OS

**A browser-based, force-directed network diagram and relationship mapping tool.**

No build step. No server. No installation. Open in any browser.

---

## What It Is

ECO.SYSTEM.OS is a single-file, zero-dependency web application for creating, visualising, and navigating relationship networks — nodes connected by directed links, simulated with D3.js physics. It runs entirely in the browser with no backend required.

Use it to map teams, systems, processes, concepts, dependencies, knowledge graphs, or any network of interconnected entities.

---

## Quickstart

1. Download `index.html`
2. Open it in any modern browser (Chrome, Firefox, Safari, Edge)
3. Click **+ Node** to start building your network

That's it.

---

## Features

### Network Editing
- **Add nodes** with name, type, status, owner, importance (0–100), tags, notes, custom properties
- **Create directed links** between nodes with optional relationship labels
- **Drag** nodes freely on the canvas; **pin** them in place
- **Double-click** or **right-click** a node to open the editor
- **Delete** nodes with one-click undo (Ctrl+Z)

### Visualisation
- **Force-directed layout** — nodes simulate physical repulsion and link attraction
- **3D force graph** — full 3D WebGL view via three.js
- **Type Clusters** — group nodes by type with D3 cluster forces
- **Animated link particles** — directional flow along every link (pause/resume with the Links button)
- **Node shapes** — filled circles, outline circles, or cards (rectangles)
- **Spectrum by Type** — assigns distinct colours to each node type
- **Invert** — switch between dark and light themes
- **Canvas background** — custom colour picker

### Properties Panel
- Click any node to inspect its **type, status, owner, importance**, and connections in the side panel
- Navigate between **Props / Index / Tags / Stats** tabs
- The Index tab ranks all nodes by importance + connection count
- The Stats tab shows graph metrics, pie charts, and top connected nodes

### Search & Filter
- **Inline search bar** (30% page width) — dims non-matching nodes in real time
- **Ctrl+K** Quick Switcher — keyboard-navigable node search
- **Filter bar** — filter by type, status, tag, or orphan nodes

### Save & Load
- **Save as JSON** — full graph export
- **Save as SVG** — vector export of the 2D canvas
- **Browser storage** — autosaves to `localStorage` and supports manual save/load
- **Drag & drop** — drop a `.json` file onto the canvas to import

### Keyboard Shortcuts
| Key | Action |
|---|---|
| `Ctrl+K` | Quick node switcher |
| `F` | Focus mode on hovered node |
| `Esc` | Close modal / exit focus |
| `Ctrl+Z` | Undo last deletion |
| `Dbl-click` | Edit node |
| `Right-click` | Edit node |

---

## Technology

| Library | Version | Purpose |
|---|---|---|
| [D3.js](https://d3js.org) | 7.8.5 | Force simulation, SVG rendering |
| [3d-force-graph](https://github.com/vasturiano/3d-force-graph) | 1.73.4 | 3D WebGL graph |
| [GSAP](https://gsap.com) | 3.12.2 | Animations |
| [Geist](https://fonts.google.com/specimen/Geist) | — | Typography (Google Fonts) |

All libraries are loaded from CDNs. No npm, no bundler, no local dependencies.

---

## File Structure

```
index.html   ← the entire application (HTML + CSS + JS, single file)
README.md    ← this file
```

---

## Browser Support

Works in all modern evergreen browsers. WebGL is required for 3D mode.

---

## Data Format

Saved JSON files follow this structure:

```json
{
  "version": "1.033",
  "nodes": [
    {
      "id": "n1a2b3c4",
      "name": "Node Name",
      "type": "System",
      "status": "Active",
      "importance": 75,
      "color": "#2203ff",
      "owners": ["Alice"],
      "tags": ["core"],
      "notes": "Description here",
      "linksOut": ["n5d6e7f8"],
      "custom": [{ "key": "Version", "val": "2.1" }],
      "pinned": false
    }
  ],
  "customTypes": [],
  "customStatuses": []
}
```

---

## Changelog

### v1.033
- Responsive mobile layout
- Blue network favicon
- Geist font throughout (replaces Sunflower)
- Properties panel: type/status/owner shown before custom properties
- Removed help/keyboard shortcut button from footer
- Search bar fixed at 30% page width
- Links button now correctly pauses animation in both 2D and 3D modes
- Importance field renamed and value is now keyboard-editable; Enter applies
- Icons removed from Visuals, Links, and Relayout buttons
- "Color by Type" renamed to "Spectrum by Type" with stronger visual contrast
- New "Invert" option in Visuals panel — toggles light/dark theme
- Type field is fully editable — create or rename types freely
- App description updated

### v1.032
- Initial public release

---

## License

For personal and internal use. Not licensed for commercial redistribution.

---

*ECO.SYSTEM.OS — map everything.*

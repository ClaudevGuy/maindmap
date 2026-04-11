# mAIndmap

A fully-featured, AI-powered mind mapping tool that runs entirely in a single HTML file — no build step, no server, no dependencies.

[Open `index.html` in your browser and start mapping.]

---

## Quick Start

**1. Clone or download**
```bash
git clone https://github.com/ClaudevGuy/maindmap.git
cd maindmap
```

**2. Open in your browser**
```bash
# macOS
open index.html

# Windows
start index.html

# Linux
xdg-open index.html
```

That's it. No `npm install`, no build, no server required.

---

## Features

### Core
- **Infinite canvas** — pan and zoom a 10,000 × 10,000 px world
- **Multi-tab maps** — open up to 10 independent maps in tabs, each with its own pan/zoom/style
- **Auto-save** — every change is debounced and written to `localStorage`
- **Undo / Redo** — full history stack (50 levels)

### Nodes
- Root → Branch → Child → Grandchild hierarchy
- Drag to reposition freely or use auto-layout
- Inline editing (double-click or F2)
- Per-node icons (emoji picker), color, tags, notes, custom shape (rect / circle / hex)
- Collapse/expand subtrees

### Layouts
| Layout | Description |
|--------|-------------|
| Radial | Default — branches radiate from center |
| Left → Right | Horizontal tree |
| Top → Down | Vertical tree |
| Free | No automatic positioning |

### Visual Styles
| Style | Look |
|-------|------|
| **Modern** | Default dark |
| **Sketched** | Caveat handwriting font, wobbly lines |
| **Neon** | Pure black, glowing strokes |
| **Paper** | Cork-board sticky-note feel |
| **Minimal** | Text only, ultra-clean |
| **Glass** | Frosted glassmorphism |
| **Retro** | Special Elite typewriter font |
| **Forest** | Deep green organic |

Switch style via the toolbar **Style ▾** button.

### Background Picker
Five canvas backgrounds — White / Cream / Gray / Dark / Black — accessible via the **BG ▾** button. The toolbar, minimap, and status bar all adapt to light or dark backgrounds automatically.

### AI Integration
Click the **★ AI** button (top-right) to open the AI panel. Requires an Anthropic API key:

1. Open the AI panel → paste your key in the **API Key** field
2. Use **Suggest**, **Expand**, or **Ask** to grow your map with Claude

### Drawing Tools
A full drawing toolbar lives on the left side:

`Select` `Pan` `Rectangle` `Diamond` `Ellipse` `Arrow` `Line` `Pen` `Text` `Eraser`

### Other Tools
- **Minimap** — live overview in the bottom-left corner, click to navigate (toggle with `M`)
- **Presentation mode** — step through top-level branches cinematically
- **Timeline / Gantt** — assign start/end dates to nodes (`Alt+T`)
- **Version history** — named snapshots with restore (`Ctrl+Shift+H`)
- **Voice input** — dictate nodes via the browser's Web Speech API
- **Canvas sticky notes** — floating notes pinned to the canvas (double-click empty space)
- **Find connections** — AI-detected conceptual links between distant nodes
- **Templates** — load a pre-built Portent architecture map
- **Import / Export** — JSON, plain text outline, Markdown, CSV, URL/content-scrape

---

## Keyboard Shortcuts

### Navigation
| Shortcut | Action |
|----------|--------|
| `Scroll` | Zoom |
| `F` | Fit to screen |
| `Ctrl+F` | Search nodes |
| `M` | Toggle minimap |
| Arrow keys | Navigate between nodes |

### Editing
| Shortcut | Action |
|----------|--------|
| `Tab` | Add child node |
| `Enter` | Add sibling node |
| `F2` / double-click | Edit label |
| `Del` | Delete selected |
| `Ctrl+Z` / `Ctrl+Y` | Undo / Redo |
| `Ctrl+C` / `Ctrl+V` | Copy / Paste subtree |

### Tabs
| Shortcut | Action |
|----------|--------|
| `Ctrl+T` | New tab |
| `Ctrl+W` | Close current tab |
| `Ctrl+Tab` | Next tab |
| `Ctrl+Shift+Tab` | Previous tab |
| `Ctrl+1–9` | Switch to tab by number |

### View
| Shortcut | Action |
|----------|--------|
| `Space` | Focus / unfocus branch |
| `Alt+Z` | Zen mode (hides UI chrome) |
| `?` | Shortcuts panel |
| `Ctrl+Shift+V` | Voice input |
| `Alt+T` | Timeline / Gantt |
| `Ctrl+Shift+H` | Version history |

---

## Data & Privacy

All data is stored **locally in your browser** via `localStorage`. Nothing is ever sent to any server unless you use the AI feature (which calls the Anthropic API directly from your browser using your own key).

To back up your maps: **Export → JSON** from the toolbar menu.

---

## Browser Compatibility

Works in any modern browser. Voice input requires Chrome or Edge (Web Speech API). Tested on Chrome 120+, Firefox 122+, Safari 17+.

---

## License

MIT

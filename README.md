# mAIndmap

A fully-featured, AI-powered mind mapping tool that runs entirely in a single HTML file — no build step, no server, no dependencies.

Open `index.html` in your browser and start mapping.

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
- **Multi-tab maps** — open up to 10 independent maps in tabs, each with its own pan/zoom/style/background
- **Auto-save** — every change is debounced and written to `localStorage`
- **Undo / Redo** — full history stack (50 levels)
- **Version history** — named snapshots with side-by-side restore (`Ctrl+Shift+H`)
- **Multiple root nodes** — place independent trees on the same canvas (`Ctrl+Shift+N`)

### Nodes

- Root → Branch → Child → Grandchild hierarchy
- Drag to reposition freely or use auto-layout
- Inline editing (double-click or `F2`)
- Per-node icons (emoji picker), color, tags, notes, custom shape (pill / rect / circle / hex)
- Collapse/expand subtrees
- Markdown rendering in labels — `**bold**`, `_italic_`, `` `code` ``, `[link](url)`
- File attachments — drag any file onto a node to attach it (📎 indicator)
- Audio notes — record a voice memo per node (`R` key, 🎵 indicator)

### Node-to-Document

Double-click any node that already has a document, or press `Ctrl+Enter` on a selected node to open a full rich-text document panel:

| Feature | Description |
|---------|-------------|
| **Rich text editor** | Bold, italic, underline, strikethrough, inline code, lists, links |
| **Slash commands** | Type `/` in the editor for heading, quote, code block, divider, checklist, and more |
| **AI Write** | Stream AI-generated content directly into the document |
| **AI Summary** | Summarise the document in one click |
| **AI Todo** | Extract action items from the document into a checklist |
| **Docs overview** | `Ctrl+Shift+D` or the Docs button — browse all node documents across your map |
| **Node indicator** | Nodes with documents show a small dot indicator |

### Layouts

| Layout | Description |
|--------|-------------|
| Radial | Default — branches radiate from center |
| Left → Right | Horizontal tree |
| Top → Down | Vertical tree |
| Fishbone | Ishikawa / cause-and-effect diagram |
| Free | No automatic positioning |

### Visual Styles

| Style | Look |
|-------|------|
| **Modern** | Clean pill nodes, smooth bezier connections |
| **Sketched** | Caveat handwriting font, turbulence filter, wobbly lines |
| **Neon** | Pure black canvas, glowing CSS box-shadows |
| **Paper** | Pastel sticky-note colors, drop shadows |
| **Minimal** | Text only, no boxes, ultra-clean |
| **Glass** | Frosted glassmorphism on dark gradient |
| **Retro** | Special Elite typewriter font, aged paper |
| **Forest** | Deep green organic palette, rounded nodes |

Switch style via the **Style ▾** button in the toolbar.

### Background Picker

Five canvas backgrounds — **White / Cream / Gray / Dark / Black** — via the **BG ▾** button. The toolbar, left panel, minimap, and status bar all adapt automatically to light or dark backgrounds.

### AI Features

Click the **✦ AI** button (bottom-right) to open the AI panel. Requires an Anthropic API key (stored locally, never sent anywhere except Anthropic's API):

| Feature | What it does |
|---------|-------------|
| **Expand node** | Generates 6 relevant child suggestions for any selected node |
| **Summarize branch** | Writes a paragraph summary of an entire subtree |
| **Find gaps** | Reviews your whole map and identifies 5 missing topics |
| **Rewrite label** | Suggests 3 clearer/more specific alternatives for a node label |
| **Generate branch** | Builds a full 3-level branch from a text description |
| **Find connections** | Draws dotted arcs between non-connected nodes that are conceptually related |
| **AI auto-refresh** | Detects nodes not updated in 30+ days and suggests what to add |
| **Ask anything** | Chat with Claude about your map — summarize, plan, prioritize |
| **Import from content** | Drop a PDF, text file, or paste a URL — AI converts it to a map |

### Drawing Tools

A full drawing toolbar on the left side of the canvas:

| Tool | Key | Description |
|------|-----|-------------|
| Select | `V` | Select and move nodes; click a drawn shape to select it, then `Del` to delete |
| Pan | `H` | Pan the canvas |
| Box select | `S` | Drag to select multiple nodes |
| Rectangle | `R` | Draw a rectangle shape |
| Diamond | `D` | Draw a diamond shape |
| Ellipse | `O` | Draw an ellipse |
| Arrow | `A` | Draw an arrow |
| Line | `L` | Draw a line |
| Pen | `P` | Freehand drawing |
| Text | `T` | Place a floating text box |
| Image | `9` | Place an image from file |
| Frame | `F` | Draw a labeled container |
| Eraser | `E` | Remove drawn elements |
| Note | `N` | Place a sticky note |

> **Tip:** Right-click any drawn shape (rectangle, diamond, ellipse, etc.) to instantly delete it.

### Import

| Format | How |
|--------|-----|
| Text outline | Paste indented text — 2 spaces = 1 level deep |
| Markdown headings | `# Root` `## Branch` `### Child` |
| AI generate | Describe a topic — Claude builds the full map |
| PDF / file | Drop onto canvas — AI extracts structure |
| URL | Paste any URL — AI fetches and maps the content |
| JSON | Drag a previously exported `.json` file |

### Export

| Format | Description |
|--------|-------------|
| PNG | High-resolution 2× image |
| SVG | Infinitely scalable vector |
| PDF | A4 landscape via browser print |
| Markdown | Nested `#` heading outline |
| CSV | One row per node — label, parent, depth, branch, tags |
| JSON | Full map data for re-import |
| Text outline | Indented plain text |
| Share link | Entire map encoded as a base64 URL hash |

### Other Tools

- **Minimap** — live overview bottom-left, click to navigate, reflects zoom/pan in real time (toggle `M`)
- **Presentation mode** — animate through branches cinematically (`▷` in toolbar)
- **Voice input** — dictate nodes via Web Speech API, real-time node creation (`Ctrl+Shift+V`)
- **Canvas sticky notes** — floating notes anywhere on canvas, 6 colors, resizable, connectable to nodes
- **Focus mode** — dims everything except the selected branch (`Space`)
- **Zen mode** — hides all UI chrome for distraction-free mapping (`Alt+Z`); a dismiss notice appears top-right
- **Smart search** — highlights matching nodes, cycles through results (`Ctrl+F` or `/`)
- **Multi-select** — `Shift+click` or box select, then drag all selected nodes together
- **Align tools** — align/distribute multiple selected nodes (top, bottom, left, right, center, distribute)
- **Templates gallery** — 20 pre-built maps: SWOT, Business Model Canvas, OKRs, Project Plan, and more
- **Toggle grid** — dots or lines grid overlay via the `☰` menu; active state shown with a checkmark

---

## Keyboard Shortcuts

### Navigation

| Shortcut | Action |
|----------|--------|
| `Scroll` | Zoom in/out |
| `F` | Fit to screen |
| `Ctrl+F` or `/` | Search nodes |
| `M` | Toggle minimap |
| Arrow keys | Navigate between nodes |

### Editing

| Shortcut | Action |
|----------|--------|
| `Tab` | Add child node |
| `Enter` | Add sibling node |
| `F2` / double-click | Edit label |
| `Del` / `Backspace` | Delete selected node or drawn shape |
| `Ctrl+Z` | Undo |
| `Ctrl+Y` | Redo |
| `Ctrl+C` | Copy subtree |
| `Ctrl+V` | Paste as child |
| `Ctrl+D` | Duplicate node |
| `Ctrl+Shift+N` | New root node |
| `R` | Record audio note on selected node |
| `N` | Place sticky note (then click canvas) |

### Documents

| Shortcut | Action |
|----------|--------|
| `Ctrl+Enter` | Open / close node document panel |
| `Ctrl+Shift+D` | Open documents overview |

### Saving

| Shortcut | Action |
|----------|--------|
| `Ctrl+S` | Save named snapshot |
| `Ctrl+Shift+H` | Open version history |
| `Ctrl+Shift+O` | Import from file or URL |

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
| `Alt+Z` | Zen mode |
| `Ctrl+Shift+V` | Voice input |
| `?` | Keyboard shortcuts panel |

### Tools

| Shortcut | Action |
|----------|--------|
| `V` | Select tool |
| `H` | Pan tool |
| `S` | Box select |
| `R` | Rectangle / record audio (context-sensitive) |
| `D` | Diamond |
| `O` | Ellipse |
| `A` | Arrow |
| `L` | Line |
| `P` | Pen |
| `T` | Text box |
| `E` | Eraser |
| `F` | Frame |
| `N` | Sticky note |

---

## Data & Privacy

All data is stored **locally in your browser** via `localStorage`. Nothing is ever sent to any server unless you use the AI feature — which calls the Anthropic API directly from your browser using your own key.

**To back up your maps:** Export → JSON from the toolbar. Drag the `.json` file back onto the canvas to restore.

> **Note:** Clearing your browser cache or history will delete your maps. Export regularly to keep permanent backups.

---

## Browser Compatibility

| Browser | Support |
|---------|---------|
| Chrome 120+ | Full support |
| Edge 120+ | Full support |
| Firefox 122+ | Full support (no voice input) |
| Safari 17+ | Full support (no voice input) |

Voice input (`Ctrl+Shift+V`) requires Chrome or Edge — Web Speech API only.

---

## License

MIT

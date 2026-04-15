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

- **Infinite canvas** — pan and zoom a 10,000 x 10,000 px world
- **Multi-tab maps** — open up to 10 independent maps in tabs, each with its own pan/zoom/style/background
- **Auto-save** — every change is debounced and written to `localStorage`
- **Persistent view state** — background, zoom, pan position, layout, and style all restore on reload
- **Undo / Redo** — full history stack (50 levels)
- **Version history** — named snapshots with side-by-side restore (`Ctrl+Shift+H`)
- **Multiple root nodes** — place independent trees on the same canvas (`Ctrl+Shift+N`)
- **Command palette** — quick access to any action (`Ctrl+K`)

### Nodes

- Root, Branch, Child, Grandchild hierarchy with gradient-colored branches
- Drag to reposition freely or use auto-layout
- **Drag-to-reparent** — hover over another node while dragging to move a branch to a new parent
- Inline editing (`F2`), double-click to open the node's document
- Per-node icons (emoji picker), color, tags, notes, custom shape (pill / rect / circle / hex)
- Collapse/expand subtrees
- **Slash commands** — type `/` while editing a node label for quick actions (`/image`, `/color`, `/tag`, `/bold`, etc.)
- Markdown rendering in labels — `**bold**`, `_italic_`, `` `code` ``, `[link](url)`
- File attachments — drag any file onto a node to attach it
- Audio notes — record a voice memo per node (`R` key)
- **Hover previews** — hover over a node to see notes, tags, and image thumbnails in a tooltip

### Node-to-Document

Double-click any node or press `Ctrl+Enter` on a selected node to open a full rich-text document panel:

| Feature | Description |
|---------|-------------|
| **Rich text editor** | Bold, italic, underline, strikethrough, inline code, lists, links |
| **Slash commands** | Type `/` in the editor for heading, quote, code block, divider, checklist, and more |
| **11 smart templates** | Meeting notes, decision log, product spec, project plan, research, person, goal, problem, idea, process, general note |
| **AI template detection** | Automatically suggests the best template based on node label |
| **AI pre-fill** | Stream AI-generated content into a template based on the node's context |
| **AI Write** | Stream AI-generated content directly into the document |
| **AI Summary** | Summarise the document in one click |
| **AI Todo** | Extract action items from the document into a checklist |
| **Docs overview** | `Ctrl+Shift+D` or the Docs button — browse all node documents across your map |
| **Node indicator** | Nodes with documents show a small dot indicator |

### Layouts

| Layout | Description |
|--------|-------------|
| Radial | Default — branches radiate from center |
| Left to Right | Horizontal tree |
| Top to Down | Vertical tree |
| Org Chart | Hierarchical org-style layout |
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

Switch style via the **Style** button in the toolbar.

### Color Palettes

Six curated palettes for harmonious branch coloring:

| Palette | Character |
|---------|-----------|
| Vibrant | Bold, high-contrast primary colors |
| Pastel | Soft, muted tones |
| Earth | Warm browns, greens, terracotta |
| Ocean | Blues, teals, aqua |
| Warm | Reds, oranges, yellows |
| Cool | Blues, purples, greens |

Colors are assigned sequentially (not randomly) to branches. Switch via the palette picker.

### Background Picker

Five canvas backgrounds — **White / Cream / Gray / Dark / Black** — via the **BG** button. The toolbar, panels, minimap, and status bar all adapt automatically to light or dark backgrounds. Your background choice persists across sessions.

### Themes

Four UI themes: **Dark** (default), **Light**, **Midnight**, and **Portent**. All themes adapt properly to both light and dark canvas backgrounds.

### AI Features

Click the **AI** button to open the AI panel. Requires an Anthropic API key (stored locally, never sent anywhere except Anthropic's API):

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
| Select | `V` | Select and move drawn elements; `Del` to delete |
| Pan | `H` | Pan the canvas |
| Box select | `S` | Drag to select multiple nodes |
| Rectangle | `R` | Draw a rectangle shape |
| Diamond | `D` | Draw a diamond shape |
| Ellipse | `O` | Draw an ellipse |
| Arrow | `A` | Draw an arrow |
| Line | `L` | Draw a line |
| Pen | `P` | Freehand drawing |
| Text | `T` | Place text with full formatting toolbar |
| Image | `9` | Place an image from file |
| Eraser | `E` | Remove drawn elements |
| Note | `N` | Place a sticky note |
| Boundary | `G` | Draw a named boundary region to group nodes |

### Text Formatting

Select any text element on the canvas to open the floating format toolbar:

- **Bold / Italic** toggle
- **Font size** — 7 sizes from 18px to 100px
- **Color** — 7 color swatches (white, green, amber, blue, red, purple, dark)
- **Edit** — re-edit text content
- **Duplicate / Delete**

Double-click a text element to re-edit its content directly.

### Connector Labels

Right-click a node to label the connection to its parent. Labels appear on the connection line — useful for relationships like "causes", "depends on", "leads to". Double-click a label to edit, right-click to delete.

### Boundary Regions

Press `G` or use the boundary tool to draw named regions around groups of related nodes. Boundaries have:

- Customizable label and color
- Low-opacity fill with dashed border
- Drag to move, drag corners to resize
- Right-click to rename, recolor, or delete

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
| PNG | High-resolution 2x image |
| SVG | Infinitely scalable vector |
| Markdown | Nested `#` heading outline |
| CSV | One row per node — label, parent, depth, branch, tags |
| JSON | Full map data for re-import |
| Text outline | Indented plain text (copied to clipboard) |
| Notion | Formatted for pasting into Notion |
| Obsidian vault | `.zip` with interlinked `.md` files |
| Share as HTML | Self-contained interactive HTML file |
| Social card | 1200x630 OG image for social sharing |
| Share link | Entire map encoded as a base64 URL hash |

### Presentations

- **Slides editor** — reorder branches as slides, add custom titles and notes per slide
- **Present mode** — full-screen presentation with smooth animated transitions
- **PDF / PNG export** — export all slides as PDF or individual PNGs
- Navigate with arrow keys, `Esc` to exit

### Gantt / Timeline View

Open with `Alt+T` to see task nodes on a timeline. Set start/end dates on nodes via the context menu to plan projects visually.

### Other Tools

- **Minimap** — live overview bottom-left, click to navigate, reflects zoom/pan in real time (toggle `M`)
- **Voice input** — dictate nodes via Web Speech API, real-time node creation (`Ctrl+Shift+V`)
- **Canvas sticky notes** — floating notes anywhere on canvas, 6 colors, resizable, connectable to nodes
- **Focus mode** — dims everything except the selected branch (`Space`)
- **Zen mode** — hides all UI chrome for distraction-free mapping (`Alt+Z`)
- **Smart search** — highlights matching nodes, cycles through results (`Ctrl+F` or `/`)
- **Multi-select** — `Shift+click` or box select, then drag all selected nodes together
- **Align tools** — align/distribute multiple selected nodes (top, bottom, left, right, center, distribute)
- **Templates gallery** — 20 pre-built maps: SWOT, Business Model Canvas, OKRs, Project Plan, and more
- **Feature guide** — interactive walkthrough of all features (`?` button in toolbar)
- **Map health** — AI-powered analysis of your map's completeness and structure
- **Toggle grid** — dots or lines grid overlay via the menu

---

## Keyboard Shortcuts

### Navigation

| Shortcut | Action |
|----------|--------|
| `Scroll` | Zoom in/out |
| `F` | Fit to screen |
| `Ctrl+F` or `/` | Search nodes |
| `Ctrl+K` | Command palette |
| `M` | Toggle minimap |
| Arrow keys | Navigate between nodes |

### Editing

| Shortcut | Action |
|----------|--------|
| `Tab` | Add child node |
| `Enter` | Add sibling node |
| `F2` | Edit label |
| `Double-click` | Open node document |
| `Del` / `Backspace` | Delete selected node or drawn shape |
| `Ctrl+Z` | Undo |
| `Ctrl+Y` | Redo |
| `Ctrl+C` | Copy subtree |
| `Ctrl+V` | Paste as child |
| `Ctrl+D` | Duplicate node |
| `Ctrl+Shift+N` | New root node |
| `R` | Record audio note on selected node |

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
| `Ctrl+Shift+S` | Save snapshot |

### Tabs

| Shortcut | Action |
|----------|--------|
| `Ctrl+T` | New tab |
| `Ctrl+W` | Close current tab |
| `Ctrl+Tab` | Next tab |
| `Ctrl+Shift+Tab` | Previous tab |
| `Ctrl+1-9` | Switch to tab by number |

### View

| Shortcut | Action |
|----------|--------|
| `Space` | Focus / unfocus branch |
| `Alt+Z` | Zen mode |
| `Alt+T` | Gantt / timeline view |
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
| `T` | Text (with formatting toolbar) |
| `E` | Eraser |
| `N` | Sticky note |
| `G` | Boundary region |

---

## Data & Privacy

All data is stored **locally in your browser** via `localStorage`. Nothing is ever sent to any server unless you use the AI feature — which calls the Anthropic API directly from your browser using your own key.

**To back up your maps:** Export as JSON from the toolbar. Drag the `.json` file back onto the canvas to restore.

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

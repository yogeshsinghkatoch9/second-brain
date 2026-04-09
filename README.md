# Second Brain

A powerful, self-contained knowledge graph that runs entirely in your browser. No server, no dependencies, no sign-up. Just open `index.html` and start thinking.

**[Live Demo](https://yogeshsinghkatoch9.github.io/second-brain/)** | Single HTML file | ~7,800 lines | Zero dependencies

![Second Brain Screenshot](https://img.shields.io/badge/Status-Active-green) ![License](https://img.shields.io/badge/License-MIT-blue) ![Size](https://img.shields.io/badge/Size-~250KB-orange)

---

## What is this?

Second Brain is an interactive knowledge graph — a visual tool for saving ideas, connecting thoughts, and building a persistent thinking workspace. Everything saves to your browser's localStorage and persists across sessions.

Think of it as a mix of Obsidian, Miro, and Notion — but in a single HTML file you can run offline.

---

## Features

### Core
- **Infinite Canvas** — Pan, zoom, and navigate freely with mouse or trackpad
- **Nodes** — Create, edit, resize, color-code, and tag notes with rich markdown
- **Connections** — Link nodes with typed, labeled, weighted edges (relates, supports, contradicts, causes, follows)
- **Auto-Save** — Everything persists to localStorage with 500ms debounce
- **Multiple Projects** — Switch between separate knowledge graphs
- **Undo/Redo** — Full history stack with visual buttons

### Views
- **Kanban Board** — Group nodes by tag or color into draggable columns
- **Timeline View** — Chronological view of all nodes by created/modified date
- **Calendar View** — Month grid with daily notes and node mapping
- **Pin Board** — Cork board layout with sticky notes and push pins
- **Graph View** — Force-directed graph visualization
- **Relationship Matrix** — Table view showing all node-to-node connections
- **Presentation Mode** — Step through nodes as slides
- **Focus Mode** — Spotlight a node and its neighbors, dim everything else

### Editing
- **Markdown Support** — Bold, italic, links, lists, headings in node bodies
- **Wiki Links** — Type `[[` to link nodes with autocomplete
- **@ Mentions** — Type `@` to search and insert node references
- **Search & Replace** — Find and replace text across all nodes
- **Node Templates** — Meeting Notes, Project Brief, Decision Log, Bug Report, Research Note, Daily Journal
- **Inline Connection Labels** — Double-click any connection label to edit

### Organization
- **Tags** — Add, filter, and manage tags with a dedicated Tag Manager
- **Color Coding** — 8 colors with filtering in the sidebar
- **Bookmarks/Favorites** — Star important nodes for quick access bar
- **Node Voting** — Upvote/downvote for prioritization, sort by score
- **Auto-Clustering** — Label propagation algorithm detects communities
- **Node Grouping** — Frame groups that auto-parent child nodes

### Tools
- **AI Summarize** — Summarize selected nodes or entire graph using NVIDIA NIM API (Llama 3.1)
- **Smart Auto-Connect** — TF-IDF cosine similarity suggests missing connections
- **Whiteboard Drawing** — Freehand pen/eraser tool with color and size controls
- **Pomodoro Timer** — 25/5/15 focus cycles attached to nodes, logs work sessions
- **Spaced Repetition** — SM-2 algorithm flashcard review of your nodes
- **Voice Notes** — Record audio memos via MediaRecorder API, attached to nodes
- **Quick Capture** — Always-visible input field for rapid node creation
- **Connection Flow Animation** — Pulsing dots traveling along edges

### Import / Export
- **JSON Export/Import** — Full data backup and restore
- **PNG Export** — Visible area or full graph capture
- **Markdown Export** — Full graph as structured markdown with TOC
- **Standalone HTML Export** — Self-contained shareable file
- **Clipboard Import** — Paste text, outlines, or lists as connected nodes
- **Drag & Drop Files** — Drop images, text files, or PDFs onto canvas/nodes

### Collaboration
- **P2P Sync** — BroadcastChannel-based real-time sync between browser tabs
- **Version History** — Automatic snapshots with restore and diff comparison

### Polish
- **Dark/Light Theme** — Toggle or create custom themes with Theme Creator
- **Snap-to-Grid** — Toggleable 20px grid snapping with alignment guides
- **Minimap** — Click-to-navigate overview of full graph
- **Storage Quota Tracker** — Visual indicator of localStorage usage
- **Touch Support** — Pinch-zoom and two-finger pan for tablets
- **50+ Keyboard Shortcuts** — Full shortcuts overlay with `?` key
- **Command Palette** — `Cmd+K` for quick access to any action

---

## Getting Started

### Option 1: Download and open
```bash
git clone https://github.com/yogeshsinghkatoch9/second-brain.git
open second-brain/index.html
```

### Option 2: Just download the file
Download `index.html` and double-click it. That's it.

### Option 3: GitHub Pages
Visit the [live demo](https://yogeshsinghkatoch9.github.io/second-brain/).

---

## Keyboard Shortcuts

| Action | Shortcut |
|--------|----------|
| Create node | Double-click canvas |
| Quick open / Command palette | `Cmd + K` |
| Search | `Cmd + F` |
| Search & Replace | `Cmd + H` |
| Undo / Redo | `Cmd + Z` / `Cmd + Shift + Z` |
| Delete selected | `Backspace` |
| Select all | `Cmd + A` |
| Fit view | `Shift + 1` |
| Toggle draw mode | `D` |
| Toggle snap grid | `Shift + G` |
| Today's note | `Cmd + T` |
| Shortcuts help | `?` |

---

## AI Summarize Setup

The AI Summarize feature uses the NVIDIA NIM API (free tier available):

1. Go to [build.nvidia.com](https://build.nvidia.com)
2. Create an account and generate an API key
3. Click "AI" in the toolbar, then "Summarize"
4. You'll be prompted to enter your key (saved in localStorage)

---

## Tech Stack

- **Rendering**: Hybrid DOM (nodes) + SVG (connections)
- **Canvas**: CSS `transform: translate() scale()` with GPU acceleration
- **Storage**: localStorage with debounced auto-save
- **AI**: NVIDIA NIM API (Llama 3.1 8B Instruct)
- **Sync**: BroadcastChannel API
- **Audio**: MediaRecorder API
- **Drawing**: Canvas 2D API
- **Dependencies**: None. Zero. Nada.

---

## Architecture

```
index.html (single file, ~7,800 lines)
├── <style>        CSS (~860 lines) — dark/light themes, glassmorphism, responsive
├── <body>         HTML (~400 lines) — overlays, toolbar, sidebar, canvas layers
└── <script>       JS (~6,500 lines) — IIFE with strict mode
    ├── State management (localStorage, undo/redo, version history)
    ├── Canvas engine (pan, zoom, grid, minimap)
    ├── Node system (CRUD, templates, markdown, wiki-links)
    ├── Connection system (SVG bezier/straight/stepped paths, weights)
    ├── Layout engine (force-directed, snap-to-grid, alignment guides)
    ├── Views (kanban, timeline, calendar, pin board, matrix, graph, presentation)
    ├── Tools (AI, drawing, pomodoro, spaced rep, voice, search)
    ├── Import/Export (JSON, PNG, MD, HTML, clipboard, drag-drop)
    └── Collaboration (BroadcastChannel sync, version diff)
```

---

## Browser Support

| Browser | Status |
|---------|--------|
| Chrome 90+ | Full support |
| Firefox 90+ | Full support |
| Safari 15+ | Full support |
| Edge 90+ | Full support |
| Mobile Chrome/Safari | Touch support |

---

## Contributing

Contributions welcome! This is a single-file project, so:

1. Fork the repo
2. Edit `index.html`
3. Test by opening in browser
4. Submit a PR

Please keep it as a single file with zero dependencies.

---

## License

[MIT](LICENSE) — do whatever you want with it.

---

Built with obsessive attention to detail by [@yogeshsinghkatoch9](https://github.com/yogeshsinghkatoch9)

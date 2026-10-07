# Findings Map

**English** | [Русский](README.ru.md)

A single-file, offline graph editor for pentesters and researchers. Turn scattered findings into a visual map: create nodes, connect them with glowing lightning-style links, and attach notes, commands and output to every node and every link.

No installation. No server. No dependencies. Your data never leaves your browser.

<!-- Add a screenshot or GIF here: ![Findings Map](docs/screenshot.png) -->

## Features

- **Nodes in 6 shapes** (circle, square, rounded, diamond, hexagon, triangle), 3 sizes, 6 colors and 7 types (domain, IP, port, vulnerability, account, note, or none)
- **Importance 1–100**: the higher the value, the brighter the node glows
- **"Checked" status** with a live counter (`checked 3/10`), so you don't forget what is still unverified
- **Neon lightning links**: several animated, smooth, curved bolts per link (1–8, adjustable)
- **Link names as bubbles** and a hidden **description per link** for commands and code
- **Multi-select** with area selection, group dragging and bulk editing of all settings at once
- **Projects as browser-style tabs**, each with its own map
- **Search**, **undo/redo**, snap to grid, fit to screen, zoom and pan
- **Export** to JSON (backup) and Markdown (report draft); import JSON as a new project
- **Russian / English** interface
- Dark theme, works on desktop and mobile

## Quick start

1. Download `pentest-graph.html`.
2. Open it in any modern browser (Chrome, Firefox, Edge, Safari).
3. Double-click the canvas to create your first node.

**GitHub Pages (optional):** rename the file to `index.html`, then enable Pages in *Settings → Pages* to host your own copy.

## Usage guide

### Nodes

| Action | How |
|---|---|
| Create a node | Double-click the empty canvas, or press **+ Node** |
| Select a node | Click it; the side panel opens |
| Move a node | Drag it |
| Create a linked node | Select a node, press **+ Linked** in the panel |
| Duplicate / delete | Panel buttons, or `Ctrl+D` / `Delete` |

In the side panel you can set the name, type, shape, size, color, importance, the **Checked** flag, and write notes. The notes field is monospaced; `Tab` inserts an indent, so it is a good place for commands and code. A white dot on a node means it has notes.

### Links

- **Shift + drag** from one node to another, or
- press **Link** in the toolbar and click two nodes one after another (works on touch screens).

Click a link (or its bubble) to open its panel:

- **Name**: shown as a rounded bubble in the middle of the link. A link without a name stays a plain line.
- **Description**: a large monospaced field for a command, request or code. It is visible only in the panel, never on the canvas. A gray `</>` next to the name tells you a description exists.
- **Copy**, **Reverse** direction, **Delete**.

A typical pattern: put the command on the link and the result in the target node:

`[ IP ] ──(curl -i https://1.2.3.4/admin)──→ [ Server response ]`

### Multi-select

- Press **▭ Area** (toggle) or hold **Shift** and drag on the empty canvas to draw a selection rectangle.
- `Ctrl/Cmd + click` adds or removes a node; `Ctrl+A` selects everything.
- Drag any selected node to move the whole group.
- The side panel then shows bulk settings that apply to all selected nodes immediately: type, shape, size, color, importance, mark checked/unchecked, align horizontally or vertically, chain-link them, duplicate, delete.

### Projects (tabs)

- **＋** creates a project, **double-click** a tab renames it, **×** closes it (click twice to confirm; this deletes the project).
- Each project keeps its own nodes, links, view and settings.

### Search, view and history

- **Search** dims every node that does not match the name, notes or type.
- **Fit** zooms to show the whole map. Mouse wheel zooms; dragging the empty canvas pans.
- **↶ / ↷** or `Ctrl+Z` / `Ctrl+Y` undo and redo.

### Settings (⚙)

Lightning on/off, amplitude, speed, number of bolts, snap to grid, link labels on/off, clear current project. The 🌐 button switches the language.

### Export and import

- **JSON**: full backup of the current project.
- **Markdown**: checklist of nodes with notes in code blocks, plus a list of links.
- **Import**: loads a JSON file as a **new project tab** (your current project is not overwritten).

## Keyboard shortcuts

| Shortcut | Action |
|---|---|
| Double-click canvas | New node |
| Shift + drag node → node | Create link |
| Shift + drag canvas | Area selection |
| Ctrl/Cmd + click | Add/remove from selection |
| Ctrl+A | Select all |
| Ctrl+D | Duplicate selection |
| Ctrl+Z / Ctrl+Y | Undo / redo |
| Delete / Backspace | Delete selection |
| Esc | Deselect |

## Privacy and data storage

- Everything runs locally in a single HTML file. No network requests, no analytics, no accounts.
- Data is stored in your browser's `localStorage`. **Clearing browser data deletes your maps.** Export JSON regularly.
- A locally opened file and a hosted copy (e.g. GitHub Pages) use separate storage. Move maps between them with JSON export/import.
- Treat exported files carefully: they may contain client data.

## Limitations

- No real-time collaboration or cloud sync (use JSON files and Git to share maps).
- Storage size is limited by your browser (typically a few MB), which is plenty for text maps.
- On touch screens there is no Shift key; use the **Link** and **▭ Area** buttons instead.

## Contributing

Issues and pull requests are welcome. The whole app lives in one file, which keeps it easy to read and audit.

## License

Add your license here (for example MIT) and include a `LICENSE` file.

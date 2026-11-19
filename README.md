# MINDGRID

A mind mapping app in a single HTML file, styled like a green-on-black hacker terminal with falling digital rain. Map your thoughts in the browser and keep them in a real SQLite database file you own.

**Open the app:** https://fras42.github.io/mindgrid/mindgrid.html

**Current version:** 2.4

No install, no account, no server. Everything runs in your browser.

---

## Features

- Free-form mind maps with branches, multi-line nodes, indentation and bullets
- Smooth zoom into any node, overview of the whole map, and a radar minimap
- Hold a node (or right-click it) for a menu with color, connect, disconnect and delete
- Per-node colors, interface color themes, and a night/day theme
- Adjustable node widths
- Fold and unfold branches
- Undo and redo
- Auto-arrange (tidy) layout
- Saves to a standard `.sqlite` file, which you can open in any SQLite tool
- Works on desktop and on iPhone/iPad (touch, pinch-zoom, long-press)

---

## Getting started

1. Open the app link above, or download `mindgrid.html` and open it in your browser.
2. You start with one node called **central idea**. Double-click (or double-tap) it to rename it.
3. Press **Tab**, or tap **+ child**, to add a branch. Keep going.
4. Tap **save** to store your map as a `.sqlite` file.

The app needs an internet connection when it starts, to load the SQLite engine ([sql.js](https://github.com/sql-js/sql.js)) from a CDN.

---

## Controls

### Mouse and touch

| Action | What it does |
|---|---|
| Tap / click a node | Select it |
| Double-tap / double-click a node | Edit its text |
| Triple-tap a node | Add a child node |
| Double-tap / double-click empty space | Add a child of the selected node at that spot |
| Hold a node (about half a second) / right-click | Open the node menu |
| Drag a node | Move it together with its whole branch |
| Shift + drag a node | Move only that node |
| Drag the ⇔ handle on a node's right edge | Change the node's width |
| Double-tap the ⇔ handle | Reset the width to automatic |
| Drag empty space | Pan the map |
| Mouse wheel / pinch | Zoom |
| Tap a node while zoomed far out | Zoom into that node |
| Tap or drag on the radar minimap | Fly to that part of the map |
| Tap the **+N** badge on a folded node | Unfold the branch |
| Tap **? controls** (bottom right) | Show all controls; tap ✕ or the map to close |

### Keyboard (when not editing)

| Key | What it does |
|---|---|
| Tab | Add a child to the selected node |
| Enter | Add a sibling (a child, if the central node is selected) |
| F2 / Space | Edit the selected node |
| Delete / Backspace | Delete the selected node and its branch |
| Arrow keys | Move the selection to the nearest node in that direction |
| C | Fold or unfold the selected branch |
| Z | Zoom into the selected node and its branches |
| O / F / Esc | Zoom out to see the whole map |
| + / − | Zoom in / out |
| [ / ] | Make the selected node narrower / wider |
| \ | Reset the node's width to automatic |
| T | Tidy (auto-arrange) the layout |
| M | Show or hide the radar minimap |
| ? | Show the controls panel |
| Ctrl/⌘ + Z | Undo |
| Ctrl/⌘ + Y or Ctrl/⌘ + Shift + Z | Redo |
| Ctrl/⌘ + S | Save |
| Ctrl/⌘ + Shift + S | Save as a new file |
| Ctrl/⌘ + O | Open a `.sqlite` file |

### While editing a node's text

| Key / button | What it does |
|---|---|
| Enter | New line |
| Tap or click outside the node | Save the text |
| Ctrl/⌘ + Enter or **✓** | Save the text |
| Esc or **✕** | Cancel your changes |
| Tab or **⇥** | Indent the current line(s) |
| Shift + Tab or **⇤** | Outdent the current line(s) |
| **•** | Add or remove a bullet on the current line(s) |

### Node menu (hold a node or right-click)

| Item | What it does |
|---|---|
| Edit text | Start editing the node |
| Add child node | Add a branch and start typing |
| Zoom to node | Zoom into the node and its branches |
| Change color… | Pick a color for the node, optionally for its whole branch |
| Fold / Unfold branch | Hide or show everything below the node |
| Connect to another node… | Tap a new parent, and the node moves there with its branch |
| Disconnect from parent | Turn the node and its branch into a separate floating map |
| Delete node | Delete the node and everything below it |

Every change can be undone with **undo**.

### Toolbar

| Button | What it does |
|---|---|
| new | Start a new empty map |
| open | Load a map from a `.sqlite` file |
| save / save as | Save the map to a `.sqlite` file |
| + child / + sibling | Add a node |
| edit / fold / delete | Act on the selected node |
| narrower / wider | Change the selected node's width |
| undo / redo | Step back or forward |
| tidy | Auto-arrange the layout |
| zoom to node / overview | Zoom in on the selection / see everything |
| + / − | Zoom in / out |
| radar | Show or hide the minimap |
| ☀ day / ☾ night | Switch between the day and night theme |
| colors | Interface color, rain brightness, background tint |
| rain | Turn the digital rain on or off |
| ? | Controls panel (also **? controls** in the bottom-right corner) |

---

## Saving and opening maps

Your map is stored in a SQLite database file (`.sqlite`).

- **Chrome and Edge on a computer:** **save** asks for a location the first time. After that, it writes straight back to the same file.
- **Safari, Firefox and iPhone/iPad:** **save** downloads a fresh copy of the file each time. On iPhone, look in **Files → Downloads**. If you save more than once, the newest copy has the highest number, such as `mindmap-3.sqlite`.
- **open** loads a `.sqlite` file. On a computer you can also drag a file onto the window.
- Work in progress is also kept in your browser between visits, so you don't lose anything if you close the tab. This is only a safety net, because browsers (especially Safari) can clear it. **Your `.sqlite` file is your real backup, so save often.**

The status bar shows **(unsaved)** when you have changes that aren't in the file yet.

### What's inside the file

The file is a standard SQLite database, so you can open it with tools like [DB Browser for SQLite](https://sqlitebrowser.org/).

**`nodes`** holds one row per node.

| Column | Meaning |
|---|---|
| id | Node number |
| parent_id | The node it branches from (empty for a central node) |
| text | The node's text |
| x, y | Position on the map |
| collapsed | 1 if the branch is folded |
| width | Fixed width in pixels (empty = automatic) |
| color | The node's own color, such as `#ffb000` (empty = interface color) |
| created_at, updated_at | Timestamps |

**`meta`** holds map settings: the view position and zoom, the selected node, and the interface theme (color, rain, tint, night/day).

---

## Using it on iPhone or iPad

- Open the app link in **Safari**. Then tap **Share → Add to Home Screen** to get an app icon.
- Use the toolbar buttons and the hold menu in place of keyboard shortcuts.
- Double-tap a node to edit, triple-tap to add a child, hold for the menu.
- Pinch to zoom, drag with one finger to pan.
- Save often. Safari may delete a website's stored data if you don't visit it for about a week.

---

## Troubleshooting

**The app shows an old version.** The startup screen and the controls panel show the version number. Add `?v=` plus any number to the address to force a fresh copy, for example `mindgrid.html?v=24`. If you use a Home Screen icon, open the link in Safari first.

**"SQLite engine" error on startup.** The engine loads from `cdnjs.cloudflare.com`. Check your internet connection and reload.

**A file won't open.** The message at the bottom left tells you why. Make sure you pick a `.sqlite` file saved from MINDGRID, and that it isn't empty (0 bytes).

**Nodes overlap after many changes.** Press **T** or tap **tidy** to rearrange them.

**I deleted something by mistake.** Tap **undo**. If you've already closed the app, open your last saved `.sqlite` file.

---

## Version history

| Version | Changes |
|---|---|
| 2.4 | **? controls** in the bottom-right corner opens the controls panel; panel has a close button and closes when you tap the map |
| 2.3 | Night/day theme toggle; nodes grow to fit their text before wrapping |
| 2.2 | Opening `.sqlite` files works on iPhone; clear messages when a file can't be read |
| 2.1 | Version number on the startup screen; node menu scrolls on small screens |
| 2.0 | Interface colors saved in the `.sqlite` file; per-node colors; hold/right-click node menu with connect, disconnect and delete; triple-tap adds a child; text editor with indent, outdent and bullets; left-aligned text; adjustable node widths; zoom to node, overview and radar minimap; interface color themes |
| 1.0 | First release: mind map with SQLite save and open, digital rain, undo, tidy layout |

---

## Tech

- One self-contained HTML file with plain JavaScript and no build step
- [sql.js](https://github.com/sql-js/sql.js) (SQLite compiled to WebAssembly) for the database
- File System Access API for saving directly to a file where the browser supports it
- IndexedDB for the in-browser session backup

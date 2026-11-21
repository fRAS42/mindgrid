# MINDGRID

A mind mapping app in a single HTML file, styled like a green-on-black hacker terminal with falling digital rain. Map your thoughts in the browser and keep them in a real SQLite database file you own.

**Open the app:** https://fras42.github.io/mindgrid/mindgrid.html

**Current version:** 6.3

![new in 6.3](https://img.shields.io/badge/new_in-6.3-00ff41?labelColor=000000) Features in $\color{#00FF41}\textsf{matrix green}$ are new in this version.

No install, no account, no server. Everything runs in your browser.

---

## Features

- Free-form mind maps with branches, multi-line nodes, indentation and bullets
- Orbit view: travel through your map one node at a time, with the nodes inside it orbiting around it
- Full-text search across all nodes, with highlighted matches
- Table view: every leaf node (a node without children) and every node with a due date that is not done yet in a list,  newest first, with its updated time and a done checkbox
- Smooth zoom into any node, overview of the whole map, and a radar minimap
- Hold a node (or right-click it) for a menu with color, connect, disconnect and delete
- Per-node colors, interface color themes, and a night/day theme (toggle in the bottom-right corner)
- Separate color for the digital rain
- Adjustable node widths
- Geotags: pin any node to a place and open it in Maps; see all located nodes on a world map (Places view)
- Due dates for leaf nodes, shown in the table view (not on the map, to keep it tidy) and used to sort the table
- Priority flags A, B, C, D (urgent / important), shown on the node and as a column in the table
- Automatic text size: the more nodes a branch holds, the bigger its text, or set your own size per node from the node menu
- Recoloring or resizing the text of a node counts as an update; moving nodes around does not
- How long ago the selected node was updated, shown above it (for example 2 days 3 hours 14 mins ago) in text 2 sizes bigger than the node's own text; full created and updated dates in the node menu
- The most recently updated node glows in matrix green, so you can always see where you left off. A node you colored yourself keeps its own color
- The newest child of every node has a small dot on its left edge in the node's own color; the newest node in the whole map gets a matrix-green dot. Dots appear only on leaf nodes (nodes without children)
- Fold and unfold branches; focus on one topic by folding everything else. Folded nodes look like a stack of cards with a bright +N badge, and leaving focus keeps your own folds
- Undo and redo
- Auto-arrange (tidy) layout
- Saves to a standard `.sqlite` file, which you can open in any SQLite tool
- Works on desktop and on iPhone/iPad (touch, pinch-zoom, long-press)

---

## Try the demo

Download mindgrid-demo.sqlite from this repository, open the app, tap open and pick the file.

- **Download:** [mindgrid-demo.sqlite](https://github.com/fras42/mindgrid/raw/main/mindgrid-demo.sqlite)
- **On iPhone:** the file lands in **Files → Downloads**. In the app, tap **open** and choose it.

The demo is a plan for a year, MY 2027, and shows most of what the app can do:

- Colored branches (side app, learning, home, health) and the latest-updated node glowing in matrix green (Book flights)
- Priority letters A to D, due dates that are overdue, today, tomorrow and soon, and done tasks struck through
- A folded branch (Read 12 books) drawn as a stack of cards with a +5 badge
- A multi-line node with bullets and indentation, a wider node, and bigger text on the main topics
- Newest-child dots, and two separate floating maps: START HERE (quick tips) and IDEAS INBOX
- Tap the table button to see it as a to-do list, sorted by due date and priority

The due dates were set around November 20, 2026, so the longer you wait, the more of them will show as overdue.

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
| Tap / click a node | Select it and show how long ago it was last updated |
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
| Tap the **+N** badge on a folded node | Unfold the branch. Folded nodes are drawn as a stack of cards, and the bright badge shows how many nodes are hidden |
| Dot on the left edge of a node, in the node's color | This is the newest child of its parent and has no children of its own |
| Matrix-green dot on the left edge of a node | This is the newest leaf node in the whole map |
| Tap ? (bottom right) | Show all controls; tap ✕ or the map to close |
| Tap the orbit button (bottom right, next to the magnifier) | Switch between the map and the orbit view |
| Tap the pin button (dock) | Places: every located node on a world map |
| Tap the table button (bottom right, next to the magnifier) | Switch to the table view; tap it again to go back to the map |
| Tap the sun / moon button (bottom right) | Switch between the night and day theme |
| Tap the magnifier (bottom right or toolbar) | Open search |

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
| Ctrl/⌘ + F or / | Search the text of all nodes |

### While editing a node's text

| Key / button | What it does |
|---|---|
| Enter | New line |
| Tap or click outside the node | Save the text |
| Ctrl/⌘ + Enter or **✓** | Save the text |
| Esc or **✕** | Cancel your changes |
| New node | When you add a node and start typing, the view moves the node 50px up so it stays clear of the iPhone keyboard. The node's position on the map does not change |
| Tab or **⇥** | Indent the current line(s) |
| Shift + Tab or **⇤** | Outdent the current line(s) |
| **•** | Add or remove a bullet on the current line(s) |

### Due dates

Hold a leaf node (one without children) and pick a date in the Due date row of the menu. The map stays clean: the date is shown in the table view, under the node's name:

| Label | Meaning |
|---|---|
| due Fri, Nov 27 | Due a week or more from now |
| due Tue, Nov 24 (in 4 days) | Due within the next 7 days |
| due tomorrow / due today (yellow) | Due within 2 days |
| overdue 2 days (red) | The due date has passed |

Setting or removing a due date counts as an update and can be undone. Labels update by themselves when the day changes.

### Locations

Hold a node and tap Add location… to pin it to a place:

- use my current location: your phone or browser asks for permission once, then fills in the coordinates
- Place name: any name you like, for example Kyoto station
- Coordinates or a maps link: type 35.0116, 135.7681, or paste a link from Google Maps or Apple Maps
- open in maps opens the place in Apple Maps on iPhone and Mac, Google Maps elsewhere; remove clears it

Tap the pin button in the dock to open Places: a world map (Leaflet $\color{#00FF41}\textsf{with OpenStreetMap tiles, shown inverted to a dark map at night and normal by day}$) showing every located node as a glowing marker in its color. Tap a marker for its details and jump to it on the mind map, in orbit view, or in your Maps app. The map loads the first time you open Places and needs an internet connection.

A geotagged node shows a small pin on its bottom-left corner on the map and on its planet in orbit view, a 📍 line in the table, a 📍 pill in orbit view, and its place name in the node menu. Changing a location counts as an update and can be undone.

### Priority

Any node can be flagged with a priority letter from the node menu. It shows as a small colored letter on the node's bottom-right corner and in the table's PRI column.

| Flag | Meaning | Color |
|---|---|---|
| A | Urgent and important | red |
| B | Important, not urgent | amber |
| C | Urgent, not important | blue |
| D | Neither urgent nor important | grey |

In the table, tap a row's PRI cell to cycle A, B, C, D, none. Changing priority counts as an update and can be undone.

### Search

Type to search the text of every node. Matches light up and are highlighted inside the nodes; everything else fades out.

| Key / button | What it does |
|---|---|
| Type words | Find nodes that contain all the words, ignoring upper/lower case and accents (cafe finds Café) |
| Enter or ▼ | Fly to the next match |
| Shift + Enter or ▲ | Fly to the previous match |
| Tap a result in the list | Fly to that node |
| Esc or ✕ | Close search and clear the highlights |

If a match is inside a folded branch, the branch opens so you can see it. This does not change any node's updated time.

### Orbit view

Tap the orbit button in the bottom-right corner (next to the magnifier) to travel through your map instead of panning around it. Tap it again to go back to the map; the selected node stays selected.

- The node you are in sits in the middle as a glowing core with its text inside. The nodes inside it orbit around it.
- A ring around the core shows how much of everything inside is done.
- Small moons around a node show the nodes inside it; the number on it counts everything inside.
- The node you came from waits as a small ↑ orb above the core. The path at the top shows where you are; tap any part of it to go back up.
- Pills at the bottom show how many nodes are inside, % done, due date, priority and when it was last updated.

| Action | What it does |
|---|---|
| Tap a node or a moon | Go inside it |
| Tap the core | Edit its text (same editor as the map: ⇤ ⇥ • ✕ ✓) |
| Tap the ↑ orb or the path | Go back up |
| Hold a node or the core | The node menu (map-only options like fold and tidy are hidden; Zoom to node becomes Go inside) |
| Drag anywhere / mouse wheel | Spin the orbit |
| Arrow keys, Enter | Pick a node in the orbit, then go inside it |
| Tab | Add a node inside the current one |
| Backspace / Esc | Go back up |

Search and the table view work in orbit view too: picking a result takes you to that node in the orbit. Your choice of view is remembered and saved in the file.

### Table view

Tap the table button in the bottom-right corner, next to the magnifier, to see your leaf nodes (the nodes at the ends of branches, with no children) as a list, plus any node that has a due date or a priority even if it has children (marked with ▸). Tap it again (it now shows a small map icon) to go back to the map.

| Column | What it shows |
|---|---|
| NODE | The first line of the node's text, in the node's color. A thin bar on the left shows the color too |
| PRI | The priority letter. Tap it to cycle A, B, C, D, none |
| UPDATED | When the node was last updated, and how long ago |
| DONE | A checkbox to mark the node as done. The header counts how many leaf nodes are done, for example 3/12 |

- Sorting, from top to bottom:
  1. Overdue or due within 3 days, soonest due first (same day: by priority).
  2. Then by priority: A, B, C, D, then no priority.
  3. Within the same priority: earlier due date first, then the newest node first.
- A node's due date is shown under its name: red when overdue, yellow when due within 2 days.
- Nodes marked done leave the list about a second after you tick them. Tap show N done at the bottom to list them again (and hide N done to hide them).
- Tap a node's name to jump back to the map and zoom to that node. Folded branches open if needed.
- Done nodes are struck through on the map (and in the table when show done is on). Ticking done counts as an update and can be undone. The DONE count in the header always counts all leaf nodes, shown or not.
- Esc also goes back to the map. Map shortcuts (like Delete) are switched off while the table is open.

### Node menu (hold a node or right-click)

The menu fades in, and shrinks away toward your finger when it closes. The top of the menu shows when the node was created and last updated. The menu opens a little up and to the left of your finger and always stays fully on screen.

| Item | What it does |
|---|---|
| Edit text | Start editing the node |
| Add child node | Add a branch and start typing |
| Zoom to node | Zoom into the node and its branches, fitting their full width so nothing is cut off on a phone |
| Change color… | Pick a color for the node, optionally for its whole branch |
| Add location… / 📍 place | Pin the node to a place (see Locations below) |
| Due date (leaf nodes, or any node that already has one) | Pick a date with the date picker; ✕ removes it. The menu stays open |
| Priority: A / B / C / D / ✕ | Flag the node (see Priority below). Tap the active letter again or ✕ to remove it. The menu stays open |
| Text size: A− / A+ / auto | Make the node's text smaller or bigger in steps of 2. auto (highlighted when active) goes back to the automatic size. The menu stays open so you can tap several times |
| Fold / Unfold branch | Hide or show everything below the node |
| Tidy children | Neatly arrange everything below this node, leaving the node itself and the rest of the map where they are. Shown when the node has visible children |
| Focus: fold everything else | Fold every branch except this node's own branch and the path leading to it, then zoom in on it. The status bar shows focus: and the node's name |
| Exit focus (keep my folds) | Shown while focusing instead of Unfold everything. Opens only what focus folded, so branches you folded yourself stay folded. Focus is saved in the file |
| Unfold everything | Open all folded branches again (shown when something is folded and you are not in focus mode) |
| Connect to another node… | Tap a new parent, and the node moves there with its branch |
| Disconnect from parent | Turn the node and its branch into a separate floating map |
| Delete node | Delete the node and everything below it. The node, its branch and their lines fade out over about a second |
| done (bottom right) | Tick to mark the node done, untick to undo it. The menu stays open. Done nodes are struck through on the map and in the table |

Every change can be undone with **undo**.

### Toolbar

| Button | What it does |
|---|---|
| MINDGRID (logo) | About: version, where your data lives, link to this page, and a short summary of the open map |
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
| colors | Interface color, night/day, matrix-green highlight for the latest update, rain brightness, background tint |
| rain | Turn the digital rain on or off |
| rain color | Pick the rain color and brightness, separately from the interface |
| magnifier | Search the text of all nodes (also in the bottom-right corner) |
| ? | Controls panel (also ? in the bottom-right corner) |

---

## Automatic text size

Nodes that hold more below them (children, grandchildren and so on) get bigger text, so the main topics stand out on their own:

| Nodes below | Text size |
|---|---|
| none (a leaf) | 15 |
| 1 | 17 |
| 3 | 19 |
| 7 | 21 |
| 15 or more | 23, up to 26 |

A central node starts at 19 and grows up to 30. Sizes change by themselves as you add or delete nodes. A size you set with A− or A+ always wins and stays fixed; tap auto to go back to automatic.

---

## Saving and opening maps

Your map is stored in a SQLite database file (`.sqlite`).

- **Chrome and Edge on a computer:** **save** asks for a location the first time. After that, it writes straight back to the same file.
- **Safari, Firefox and iPhone/iPad:** **save** downloads a fresh copy of the file each time. On iPhone, look in **Files → Downloads**. If you save more than once, the newest copy has the highest number, such as `mindmap-3.sqlite`.
- **open** loads a `.sqlite` file. On a computer you can also drag a file onto the window.
- Work in progress is also kept in your browser between visits, so you don't lose anything if you close the tab. This is only a safety net, because browsers (especially Safari) can clear it. **Your `.sqlite` file is your real backup, so save often.**

The status bar shows **(unsaved)** when you have changes that aren't in the file yet.

The status bar also shows how long ago the map was last saved to a file, for example saved 2 hours 5 mins ago, or not saved to a file yet for a new map. The time is stored in the file, so it is still right after you open the file again.

The status bar sits under the dock, the centered row of search, orbit, places, table, day/night and ? buttons, and reads: the file name, the number of nodes (including hidden ones), the zoom level (zoom 100% = normal size), and how long ago it was saved.

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
| font_size | The node's text size in pixels, when you set it yourself (empty = automatic size) |
| done | 1 if the node is marked done in the table view, otherwise 0 |
| due | The node's due date as YYYY-MM-DD (empty = no due date) |
| category | Priority flag: A, B, C or D (empty = none) |
| lat, lon | The node's location in decimal degrees (empty = no location) |
| place | The location's name (optional) |
| created_at | When the node was created (ISO 8601, UTC) |
| updated_at | When the node's text, color, width, text size, done state, due date, priority or connection last changed (ISO 8601, UTC). Moving nodes, folding, focusing, tidy and tidy children do not change it |

**`meta`** holds map settings: the view position and zoom, the selected node, when the map was last saved to a file (file_saved_at), and the interface theme (color, rain brightness, rain color, tint, night/day, latest-update highlight).

The matrix-green highlight is not stored on the node itself. The app picks the node with the newest `updated_at` each time, and the node keeps its own `color`.

---

## Using it on iPhone or iPad

- Open the app link in **Safari**. Then tap **Share → Add to Home Screen** to get an app icon.
- Use the toolbar buttons and the hold menu in place of keyboard shortcuts.
- Double-tap a node to edit, triple-tap to add a child, hold for the menu.
- Pinch to zoom, drag with one finger to pan.
- Save often. Safari may delete a website's stored data if you don't visit it for about a week.

---

## Troubleshooting

**The app shows an old version.** The startup screen, the controls panel and the About panel (tap MINDGRID) show the version number. Add `?v=` plus any number to the address to force a fresh copy, for example `mindgrid.html?v=24`. If you use a Home Screen icon, open the link in Safari first.

**"SQLite engine" error on startup.** The engine loads from `cdnjs.cloudflare.com`. Check your internet connection and reload.

**A file won't open.** The message at the bottom left tells you why. Make sure you pick a `.sqlite` file saved from MINDGRID, and that it isn't empty (0 bytes).

**After using the table view, taps on the map do nothing.** Fixed in 4.2. Make sure the startup screen says 4.2 or later.

**Nodes overlap after many changes.** Press **T** or tap **tidy** to rearrange them.

**I deleted something by mistake.** Tap **undo**. If you've already closed the app, open your last saved `.sqlite` file.

---

## Version history

| Version | Changes |
|---|---|
| $\color{#00FF41}\textsf{6.3}$ | $\color{#00FF41}\textsf{Places view uses OpenStreetMap tiles}$ |
| 6.2 | Places view: located nodes on a Leaflet world map; bottom buttons centered like a dock |
| 6.1 | Geotags for nodes; status info moved under the bottom-right buttons |
| 6.0 | Orbit view built into MINDGRID, with its own button next to the magnifier |
| 5.9 | Hold menu simply fades in and shrinks out (scan line and ripple removed) |
| 5.8 | Slower, softer fade when deleting; hold menu appears with a scan-line effect and a ripple |
| 5.7 | Deleted nodes fade out instead of disappearing at once |
| 5.6 | Zoom to node fits whole nodes on narrow screens instead of cutting off the outer ones |
| 5.5 | Automatic text size based on how many nodes are below; manual sizes still win; default button renamed auto |
| 5.4 | Tap the MINDGRID logo for an About panel |
| 5.3 | Due dates are no longer shown under nodes on the map; they stay in the menu and the table |
| 5.2 | Tidy children in the node menu: arrange only one branch |
| 5.1 | Priority flags A–D (Eisenhower) in the node menu, on the node and as a PRI column in the table; table sorting combines due dates and priority |
| 5.0 | Nodes with children that have a due date are listed in the table too (marked ▸) and can still change or clear their due date in the menu |
| 4.9 | Only nodes due within 3 days (or overdue) move to the top of the table |
| 4.8 | Due dates for leaf nodes: date picker in the node menu, label under the node, near due dates on top of the table; Esc closes the menu even from the date field |
| 4.7 | Table view hides done nodes, with a show done / hide done button at the bottom |
| 4.6 | Exit focus keeps your own folds; folded nodes look like a stack of cards; high-contrast +N badge; focus shown in the status bar |
| 4.5 | Newest-child dots and the matrix-green newest dot only appear on leaf nodes |
| 4.4 | Day/night toggle (sun / moon) in the bottom-right buttons next to search and table |
| 4.3 | done checkbox in the node menu (bottom right); bigger search, table and ? buttons |
| 4.2 | Bug fix: after jumping from the table to a node on iPhone, the map could stop responding to taps and the table button |
| 4.1 | Table view lists only leaf nodes; node menu opens 50px further left and up and never runs off the screen edge |
| 4.0 | Newest-child dots use the node's color; only the newest node in the whole map gets a matrix-green dot |
| 3.9 | Table view (title, updated, done) with its own button next to the magnifier; done nodes struck through on the map; the help button is now just ? |
| 3.8 | Latest-update highlight no longer overrides a color you picked; newest-child dot is always matrix green |
| 3.7 | Typing into a new node lifts it 50px higher on screen |
| 3.6 | Status bar shows how long ago the map was saved to a file; zoom level is labelled zoom |
| 3.5 | Node menu: Focus (fold everything else) and Unfold everything |
| 3.4 | Full-text search (magnifier button, Ctrl+F or /) with highlighted matches, a results list and next/previous |
| 3.3 | Moving nodes no longer changes their updated time (rearranging the map is not an edit) |
| 3.2 | Color and text size changes refresh the label and menu times straight away |
| 3.1 | The how-long-ago label is 2px bigger than the node's text and follows the node's text size |
| 3.0 | The label above the selected node shows only how long ago it was updated, in days, hours and minutes |
| 2.9 | Text size controls (A−, A+, default) in the node menu, saved per node |
| 2.8 | rain color button in the toolbar: give the digital rain its own color |
| 2.7 | The newest child of every node gets a small dot on its left edge |
| 2.6 | The most recently updated node shows in matrix green with a glow (can be turned off in **colors**) |
| 2.5 | Selected node shows its last-updated time above it; node menu shows created and updated times; width changes now count as updates |
| 2.4 | **? controls** in the bottom-right corner opens the controls panel; panel has a close button and closes when you tap the map |
| 2.3 | Night/day theme toggle; nodes grow to fit their text before wrapping |
| 2.2 | Opening `.sqlite` files works on iPhone; clear messages when a file can't be read |
| 2.1 | Version number on the startup screen; node menu scrolls on small screens |
| 2.0 | Interface colors saved in the `.sqlite` file; per-node colors; hold/right-click node menu with connect, disconnect and delete; triple-tap adds a child; text editor with indent, outdent and bullets; left-aligned text; adjustable node widths; zoom to node, overview and radar minimap; interface color themes |
| 1.0 | First release: mind map with SQLite save and open, digital rain, undo, tidy layout |

---

## Tech

- Leaflet 1.9.4 (loaded on demand) with $\color{#00FF41}\textsf{OpenStreetMap}$ map tiles for the Places view

- One self-contained HTML file with plain JavaScript and no build step
- [sql.js](https://github.com/sql-js/sql.js) (SQLite compiled to WebAssembly) for the database
- File System Access API for saving directly to a file where the browser supports it
- IndexedDB for the in-browser session backup

# Gantt Chart Editor

A lightweight, interactive Gantt chart that runs entirely in a single HTML file — no install, no server, no dependencies. Open `index.html` <https://ty10y.github.io/Gantt-Chart/> in any modern browser and start planning.

---

## How to Use

### Getting started
1. Download or clone this repository.
2. Open `index.html` in your browser.
3. The chart loads with sample tasks, automatically shifted so the timeline starts today. Replace them with your own.

### Managing tasks
- Click **+ Add Task** to append a new row, defaulted to today's date.
- Edit a task name directly in the table or by clicking the label on the chart.
- Pick start and end dates using the date pickers in each row.
- Enter a **Progress** value (0–100) to track completion.
- Click **✕** to delete a task.
- Use the **▲ / ▼** buttons or drag the grip handle to reorder tasks — rows nudge out of the way live as you drag, both in the table and on the chart.

### Working with the chart
- **Move a bar** — click and drag its body left or right to shift both dates at once, without changing the task's duration.
- **Resize a bar** — drag the left or right edge to adjust the start or end date independently.
- **Open bar menu** — click a bar without dragging to get link / unlink options.
- **Link a bar** — links the task visually to the one above it with a connector line and indents its label.
- **Freeze task names** — the task-name column stays pinned on the left as you scroll the timeline horizontally. Drag the vertical divider next to it to widen or narrow the column to fit your task names.

### Saving and loading
- Click the **Export JSON** button (floppy-disk icon) to download the chart's data as a `.json` file.
- Click the **Import JSON** button (download icon) to load a previously exported `.json` file.

### Exporting the chart
- Click the **Export Chart** button (printer icon) and choose:
  - **Fit to One Page (PDF)** — the whole chart shrunk to fit on a single landscape page.
  - **Full Size, Multiple Pages (PDF)** — tiled at full, readable size across as many pages as needed, with the task names and date header repeated on every page so each one stands on its own.
  - **Download as Image (PNG)** — one full-resolution image of the entire chart.
- The chart is redrawn independently for export, so nothing gets cut off, split awkwardly, or scaled down too small to read.
- PDF export loads a small library from the internet the first time you use it; PNG export works fully offline.

---

## Features

### Task management
- Add, rename, delete, and reorder tasks
- Drag-and-drop reordering in both the task table and the chart, with a live animated "nudge" as rows make room
- Progress tracking per task (0–100 %) with a visual fill on each bar
- New tasks default to today's date

### Interactive chart
- Drag a bar's body to move a task to new dates, shifting start and end together so duration never changes
- Resize bars from either edge to extend or shorten a task
- Click a bar to open a context menu for linking / unlinking
- Linked tasks display a connector line to the task above and receive an indented label

### Timeline display
- Month and day headers that auto-fit to your date range
- Today's date highlighted with a distinct column
- Weekend columns shaded for easy visual separation
- Sample tasks automatically shift to start from today's date on load
- Frozen, resizable task-name column with its own header — stays visible while scrolling horizontally, and its width can be dragged to fit longer names

### Chart title
- Click the title at the top to rename the chart inline

### Toggle view
- Hide or show the task table without losing data

### Import / Export
- Export the full chart (title + all tasks) to a `.json` file
- Re-import any previously exported `.json` to restore the chart

### Export chart
- Export as a PDF — either shrunk to fit one page, or tiled across multiple pages at full size — or as a single PNG image
- Every exported page is self-contained, repeating the task names and date header
- Rendered on a canvas independent of the on-screen layout, so output is never cut off or illegibly small

---

## Revision History

### v2 — 2026-09-22
Major update to the interactive editor and export workflow:
- Drag-and-drop task reordering now animates smoothly, with other rows nudging out of the way live instead of jumping into place
- Dragging a bar's body moves the whole task (start and end shift together, duration unchanged) — the edge handles still resize start or end independently
- The task-name column is now frozen while scrolling horizontally, with its own header and a draggable divider to resize it
- Sample tasks load anchored to today's date, and new tasks default to today
- Darker, more visible weekend/today/header highlighting, plus general visual polish (row hover state, softer buttons, subtle shadows)
- Replaced browser-based printing with a built-in exporter: fit the whole chart to one page, tile it across multiple full-size pages with repeating headers, or save a plain image — solving the cut-off/scaling problems of printing directly from the browser

### Documentation update — 2026-05-13
- Added the project README: usage guide and full feature list

### Initial release — 2026-05-07
- Editable task table with add/delete/reorder and drag-and-drop
- Draggable, resizable bars on the chart
- Link/unlink tasks with a connector line between them
- JSON export/import to save and reload a chart
- Sticky task labels while scrolling
- One-click browser print, auto-scaled to fit A4 landscape
